### <a name="certificate-eku-oid-validation"></a>EKU-OID-Zertifikatüberprüfung

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 führt die Klasse <xref:System.Net.Security.SslStream> oder <xref:System.Net.ServicePointManager> eine Überprüfung mithilfe der erweiterten Schlüsselverwendung (EKU) und unter Berücksichtigung von Objektbezeichnern (OIDs) durch. Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden. Bei der EKU-OID-Überprüfung werden Remotezertifikatrückrufe verwendet, um sicherzustellen, dass das Remotezertifikat über die richtigen OIDs für den entsprechenden Zweck verfügt.|
|Vorschlag|Wenn diese Änderung nicht erwünscht ist, können Sie die EKU-OID-Zertifikatüberprüfung deaktivieren, indem Sie die folgende Option [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) im [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Element Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontCheckCertificateEKUs=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt. Abgesehen davon wird die Verwendung nicht empfohlen.</blockquote> |
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

