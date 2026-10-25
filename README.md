<!doctype html>
<html lang="de">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>KOSmos – Installation</title>
<link rel="icon" href="assets/icon-32.png">
<style>
:root{--bg:#f4f6f9;--card:#fff;--ink:#1d2228;--ink2:#5a636e;--line:#dfe3e8;--accent:#185abd;--ok:#1e7b45;--okbg:#e7f5ec;--warn:#8a5300;--warnbg:#fff4df}
@media (prefers-color-scheme: dark){:root{--bg:#1c1e22;--card:#26292e;--ink:#eceef1;--ink2:#a7afb9;--line:#3a3e45;--accent:#6ea8fe;--ok:#7fd3a2;--okbg:#1f3329;--warn:#f0b75a;--warnbg:#3a2f1a}}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);font:15px/1.55 -apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif}
.wrap{max-width:760px;margin:0 auto;padding:32px 16px 60px}
header{display:flex;gap:14px;align-items:center;margin-bottom:22px}
header img{width:52px;height:52px;border-radius:12px}
h1{font-size:26px;margin:0;letter-spacing:-.3px}
header p{margin:2px 0 0;color:var(--ink2)}
.card{background:var(--card);border:1px solid var(--line);border-radius:12px;padding:18px 20px;margin-top:14px}
h2{font-size:17px;margin:0 0 8px;display:flex;gap:10px;align-items:center}
.n{flex:none;width:26px;height:26px;border-radius:50%;background:var(--accent);color:#fff;font-size:13px;display:flex;align-items:center;justify-content:center;font-weight:700}
ol{margin:6px 0 0;padding-left:22px}
li{margin:4px 0}
code,kbd{font-family:ui-monospace,Menlo,monospace;font-size:13px;background:var(--bg);border:1px solid var(--line);border-radius:5px;padding:1px 5px}
.btn{display:inline-block;background:var(--accent);color:#fff;text-decoration:none;border:none;border-radius:8px;padding:10px 16px;font-weight:600;cursor:pointer;font-size:15px}
.btn.sec{background:transparent;color:var(--accent);border:1px solid var(--accent)}
.note{border-radius:8px;padding:10px 12px;margin-top:10px;font-size:14px}
.ok{background:var(--okbg);color:var(--ok)}
.warn{background:var(--warnbg);color:var(--warn)}
.row{display:flex;gap:10px;flex-wrap:wrap;margin-top:12px}
.muted{color:var(--ink2);font-size:14px}
</style>
</head>
<body>
<div class="wrap">
  <header>
    <img src="assets/icon-128.png" alt="">
    <div><h1>KOSmos</h1><p>Koordinatensysteme für Arbeitsblätter – als Seitenleiste in Word</p></div>
  </header>

  <div class="card">
    <h2><span class="n">1</span>Online stellen</h2>
    <div id="stHost"></div>
    <p class="muted">Word lädt Add-ins nur von einer https-Adresse. GitHub Pages ist dafür kostenlos:</p>
    <ol>
      <li>Auf <b>github.com</b> anmelden und ein neues, öffentliches Repository namens <code>kosmos</code> anlegen.</li>
      <li>Im Repository „uploading an existing file“ wählen und <b>alle Dateien und den Ordner <code>assets</code></b> aus diesem Paket hineinziehen, dann „Commit changes“.</li>
      <li><b>Settings → Pages</b>: bei „Branch“ <code>main</code> und <code>/ (root)</code> wählen, „Save“.</li>
      <li>Nach etwa einer Minute ist diese Seite unter <code>https://DEIN-NAME.github.io/kosmos/</code> erreichbar. Dort geht es mit Schritt 2 weiter.</li>
    </ol>
  </div>

  <div class="card">
    <h2><span class="n">2</span>Manifest herunterladen</h2>
    <p class="muted">Das Manifest sagt Word, wo KOSmos liegt. Es wird passend zu dieser Adresse erzeugt.</p>
    <div class="row"><button class="btn" id="dl" type="button">manifest.xml herunterladen</button></div>
    <div id="stManifest"></div>
  </div>

  <div class="card">
    <h2><span class="n">3</span>In Word einbinden – Mac</h2>
    <ol>
      <li>Word beenden.</li>
      <li>Im Finder <kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd> drücken und eingeben:<br><code>~/Library/Containers/com.microsoft.Word/Data/Documents/</code></li>
      <li>Dort einen Ordner <code>wef</code> anlegen, falls er fehlt, und die <code>manifest.xml</code> hineinlegen.</li>
      <li>Word starten und ein Dokument öffnen: Registerkarte <b>Start</b> → ganz rechts <b>Add-Ins</b> → <b>KOSmos</b> wählen.</li>
      <li>Ab jetzt gibt es auf der Registerkarte <b>Start</b> den Knopf <b>Koordinatensystem</b>.</li>
    </ol>
  </div>

  <div class="card">
    <h2><span class="n">3</span>In Word einbinden – Windows</h2>
    <p class="muted">Unter Windows liest Word Add-ins aus einem freigegebenen Ordner. Das geht mit Microsoft 365 oder Word 2019 und neuer.</p>
    <ol>
      <li>Einen Ordner anlegen, z. B. <code>C:\KOSmos</code>, und die <code>manifest.xml</code> hineinlegen.</li>
      <li>Rechtsklick auf den Ordner → <b>Eigenschaften → Freigabe → Freigeben</b>. Den angezeigten Netzwerkpfad notieren, z. B. <code>\\MEIN-PC\KOSmos</code>.</li>
      <li>In Word: <b>Datei → Optionen → Trust Center → Einstellungen für das Trust Center → Kataloge vertrauenswürdiger Add-Ins</b>.</li>
      <li>Bei „Katalog-URL“ den Netzwerkpfad eintragen, <b>Katalog hinzufügen</b>, Haken bei <b>Im Menü anzeigen</b>, OK. Word neu starten.</li>
      <li><b>Start → Add-Ins → Weitere Add-Ins</b> → Reiter <b>Freigegebener Ordner</b> → <b>KOSmos</b> → Hinzufügen.</li>
    </ol>
    <p class="muted">Auf Schulrechnern ist diese Einstellung oft gesperrt. Dann kann die Schul-IT KOSmos mit derselben manifest.xml zentral im Microsoft-365-Admin-Center verteilen.</p>
  </div>

  <div class="card">
    <h2>Ohne Word ausprobieren</h2>
    <p class="muted">Dieselbe Oberfläche im Browser – dort kann man das KOS als PNG (600 dpi) oder SVG speichern und in jedes Dokument ziehen.</p>
    <div class="row"><a class="btn sec" href="preview.html">Im Browser öffnen</a></div>
  </div>
</div>

<script>
var TEMPLATE = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<OfficeApp xmlns=\"http://schemas.microsoft.com/office/appforoffice/1.1\"\n           xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"\n           xmlns:bt=\"http://schemas.microsoft.com/office/officeappbasictypes/1.0\"\n           xmlns:ov=\"http://schemas.microsoft.com/office/taskpaneappversionoverrides\"\n           xsi:type=\"TaskPaneApp\">\n  <Id>50244c3d-7a23-4a7c-bb9e-15bea0f0d241</Id>\n  <Version>1.0.0.0</Version>\n  <ProviderName>KOSmos</ProviderName>\n  <DefaultLocale>de-DE</DefaultLocale>\n  <DisplayName DefaultValue=\"KOSmos\"/>\n  <Description DefaultValue=\"Koordinatensysteme, Funktionsgraphen, Messpunkte und Wertetabellen f\u00fcr Arbeitsbl\u00e4tter.\"/>\n  <IconUrl DefaultValue=\"{{BASE}}assets/icon-32.png\"/>\n  <HighResolutionIconUrl DefaultValue=\"{{BASE}}assets/icon-64.png\"/>\n  <SupportUrl DefaultValue=\"{{BASE}}\"/>\n  <AppDomains>\n    <AppDomain>{{ORIGIN}}</AppDomain>\n  </AppDomains>\n  <Hosts>\n    <Host Name=\"Document\"/>\n  </Hosts>\n  <Requirements>\n    <Sets DefaultMinVersion=\"1.1\">\n      <Set Name=\"WordApi\" MinVersion=\"1.3\"/>\n    </Sets>\n  </Requirements>\n  <DefaultSettings>\n    <SourceLocation DefaultValue=\"{{BASE}}taskpane.html\"/>\n  </DefaultSettings>\n  <Permissions>ReadWriteDocument</Permissions>\n  <VersionOverrides xmlns=\"http://schemas.microsoft.com/office/taskpaneappversionoverrides\" xsi:type=\"VersionOverridesV1_0\">\n    <Hosts>\n      <Host xsi:type=\"Document\">\n        <DesktopFormFactor>\n          <GetStarted>\n            <Title resid=\"GetStarted.Title\"/>\n            <Description resid=\"GetStarted.Description\"/>\n            <LearnMoreUrl resid=\"GetStarted.LearnMoreUrl\"/>\n          </GetStarted>\n          <FunctionFile resid=\"Commands.Url\"/>\n          <ExtensionPoint xsi:type=\"PrimaryCommandSurface\">\n            <OfficeTab id=\"TabHome\">\n              <Group id=\"KOSmos.Group\">\n                <Label resid=\"Group.Label\"/>\n                <Icon>\n                  <bt:Image size=\"16\" resid=\"Icon.16\"/>\n                  <bt:Image size=\"32\" resid=\"Icon.32\"/>\n                  <bt:Image size=\"80\" resid=\"Icon.80\"/>\n                </Icon>\n                <Control xsi:type=\"Button\" id=\"KOSmos.Open\">\n                  <Label resid=\"Button.Label\"/>\n                  <Supertip>\n                    <Title resid=\"Button.Label\"/>\n                    <Description resid=\"Button.Tooltip\"/>\n                  </Supertip>\n                  <Icon>\n                    <bt:Image size=\"16\" resid=\"Icon.16\"/>\n                    <bt:Image size=\"32\" resid=\"Icon.32\"/>\n                    <bt:Image size=\"80\" resid=\"Icon.80\"/>\n                  </Icon>\n                  <Action xsi:type=\"ShowTaskpane\">\n                    <TaskpaneId>KOSmosPane</TaskpaneId>\n                    <SourceLocation resid=\"Taskpane.Url\"/>\n                  </Action>\n                </Control>\n              </Group>\n            </OfficeTab>\n          </ExtensionPoint>\n        </DesktopFormFactor>\n      </Host>\n    </Hosts>\n    <Resources>\n      <bt:Images>\n        <bt:Image id=\"Icon.16\" DefaultValue=\"{{BASE}}assets/icon-16.png\"/>\n        <bt:Image id=\"Icon.32\" DefaultValue=\"{{BASE}}assets/icon-32.png\"/>\n        <bt:Image id=\"Icon.80\" DefaultValue=\"{{BASE}}assets/icon-80.png\"/>\n      </bt:Images>\n      <bt:Urls>\n        <bt:Url id=\"Commands.Url\" DefaultValue=\"{{BASE}}commands.html\"/>\n        <bt:Url id=\"Taskpane.Url\" DefaultValue=\"{{BASE}}taskpane.html\"/>\n        <bt:Url id=\"GetStarted.LearnMoreUrl\" DefaultValue=\"{{BASE}}\"/>\n      </bt:Urls>\n      <bt:ShortStrings>\n        <bt:String id=\"GetStarted.Title\" DefaultValue=\"KOSmos ist bereit\"/>\n        <bt:String id=\"Group.Label\" DefaultValue=\"KOSmos\"/>\n        <bt:String id=\"Button.Label\" DefaultValue=\"Koordinatensystem\"/>\n      </bt:ShortStrings>\n      <bt:LongStrings>\n        <bt:String id=\"GetStarted.Description\" DefaultValue=\"Auf der Registerkarte Start auf \u201eKoordinatensystem\u201c klicken.\"/>\n        <bt:String id=\"Button.Tooltip\" DefaultValue=\"Koordinatensystem mit Funktionsgraphen, Messpunkten oder Wertetabelle erstellen.\"/>\n      </bt:LongStrings>\n    </Resources>\n  </VersionOverrides>\n</OfficeApp>\n";
(function () {
  var online = location.protocol === 'https:';
  var base = location.href.replace(/[?#].*$/, '').replace(/[^/]*$/, '');
  var origin = location.origin;
  var stHost = document.getElementById('stHost'), stMan = document.getElementById('stManifest');
  stHost.innerHTML = online
    ? '<div class="note ok">Erledigt – diese Seite läuft unter <b>' + base.replace(/&/g, '&amp;').replace(/</g, '&lt;') + '</b></div>'
    : '<div class="note warn">Diese Seite ist gerade nur lokal geöffnet. Bitte zuerst online stellen.</div>';
  if (!online) stMan.innerHTML = '<div class="note warn">Das Manifest lässt sich erst erzeugen, wenn die Seite online ist.</div>';
  document.getElementById('dl').addEventListener('click', function () {
    if (!online) { alert('Bitte die Seite zuerst online stellen (Schritt 1) und dort öffnen.'); return; }
    var xml = TEMPLATE.split('{{BASE}}').join(base).split('{{ORIGIN}}').join(origin);
    var a = document.createElement('a');
    a.href = URL.createObjectURL(new Blob([xml], { type: 'application/xml' }));
    a.download = 'manifest.xml';
    document.body.appendChild(a); a.click(); a.remove();
  });
})();
</script>
</body>
</html>
