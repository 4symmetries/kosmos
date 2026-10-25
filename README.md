<body>
<div class="wrap">
  <header>
    <img src="assets/icon-128.png" alt="">
    <div><h1>KOSmos</h1><p>Koordinatensysteme für Arbeitsblätter – als Seitenleiste in Word</p></div>
  </header>


  <div class="card">
    <h2><span class="n">1 </span>Manifest herunterladen</h2>
    <p class="muted">Das Manifest sagt Word, wo KOSmos liegt. Es wird passend zu dieser Adresse erzeugt.</p>
  </div>

  <div class="card">
    <h2><span class="n">2 </span>In Word einbinden – Mac</h2>
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


</body>
</html>
