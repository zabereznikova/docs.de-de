---
title: AppContextSwitchOverrides-Element
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 8d5cd73bb9393533cb669581420e24297cb5ff71
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102930"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides>-Element

Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<AppContextSwitchOverrides>**

## <a name="syntax"></a>Syntax

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`value`|Erforderliches Attribut.<br /><br /> Definiert einen oder mehrere Wechselnamen und die zugehörigen booleschen Werte.|

### <a name="value-attribute"></a>value-Attribut

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|"name=Wert"|Ein vordefinierter Schaltername zusammen`true` `false`mit seinem Wert ( oder ). Mehrere Schaltername/Wertpaare werden durch Semikolons (";") getrennt. Eine Liste vordefinierter Switchnamen, die von .NET Framework unterstützt werden, finden Sie im Abschnitt "Hinweise".|

### <a name="child-elements"></a>Untergeordnete Elemente
 Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|

## <a name="remarks"></a>Bemerkungen
 Ab .NET Framework 4.6 `<AppContextSwitchOverrides>` kann das Element in einer Konfigurationsdatei Aufrufern einer API bestimmen, ob ihre App die neuen Funktionen nutzen oder die Kompatibilität mit früheren Versionen einer Bibliothek beibehalten kann. Wenn sich beispielsweise das Verhalten einer API zwischen zwei Versionen `<AppContextSwitchOverrides>` einer Bibliothek geändert hat, ermöglicht das Element Aufrufern dieser API, das neue Verhalten für Versionen der Bibliothek, die die neue Funktionalität unterstützen, zu deaktivieren. Für Apps, die APIs in .NET Framework aufrufen, kann das `<AppContextSwitchOverrides>` Element auch Aufrufern, deren Apps auf eine frühere Version von .NET Framework abzielen, erlauben, sich für neue Funktionen zu entscheiden, wenn ihre App auf einer Version von .NET Framework ausgeführt wird, die diese Funktionalität enthält.

 Das `value` Attribut `<AppContextSwitchOverrides>` des Elements besteht aus einer einzelnen Zeichenfolge, die aus einem oder mehreren durch Semikolons getrennten Namens-Wert-Paaren besteht.  Jeder Name identifiziert einen Kompatibilitätsschalter, und der`true` entsprechende `false`Wert ist ein boolescher ( oder ) Wert, der angibt, ob der Schalter gesetzt ist. Standardmäßig ist `false`der Schalter , und Bibliotheken stellen die neue Funktionalität bereit. Sie stellen nur die vorherige Funktionalität bereit, wenn der `true`Schalter gesetzt ist (d. h., sein Wert ist ). Dadurch können Bibliotheken neues Verhalten für eine vorhandene API bereitstellen und gleichzeitig Aufrufern, die vom vorherigen Verhalten abhängig sind, ermöglichen, sich von der neuen Funktionalität abzumelden.

.NET Framework unterstützt die folgenden Switches:

|Switch-Name|BESCHREIBUNG|Eingeführt|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Steuert, ob Windows Presentation Foundation einen Legacyalgorithmus für das Steuerelementlayout verwendet. Weitere Informationen finden Sie unter [Entschärfung: WPF-Layout](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Steuert, ob der Standardalgorithmus, der zum Signieren von Teilen eines Pakets von PackageDigitalSignatureManager verwendet wird, SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Wenn auf `false`festgelegt, können XAML-basierte Workflowprojekte mit Visual Studio gedebugpft werden, wenn FIPS aktiviert ist. Andernfalls wird <xref:System.NullReferenceException> ein in Aufrufen von Methoden in der System.Activities-Assembly ausgelöst.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Steuert, ob die Prüfsumme für eine Workflowinstanz im Debugger MD5 oder SHA1 verwendet. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Steuert, ob Workflow-Prüfsummen-Hashing den SHA1-Algorithmus verwendet, der`true`als Standard in .NET Framework 4.7 ( ) eingeführt wurde,`false`oder ob der standardmäßige SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4.8 ( ) eingeführt wurde.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Steuert, ob Stapelablaufverfolgungen bei Verwendung von portablen PDBs Quelldatei- und Leitungsinformationen enthalten können. `false`Quelldatei- und Zeileninformationen einzuschließen; andernfalls `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Steuert, <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> ob die Methode <xref:System.Drawing.Icon> eine Ausnahme auslöst, wenn ein Objekt ÜBER PNG-Frames verfügt. Weitere Informationen finden Sie unter [Entschärfung: PNG-Bilder in Symbolobjekten](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Bestimmt, <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> ob Objekte ordnungsgemäß verworfen werden, <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> wenn sie der Auflistung von der Methode hinzugefügt werden. `true`das Legacy-Verhalten beizubehalten; `false` , um alle privaten Schriftartobjekte zu entsorgen. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Steuert, ob die <xref:System.Windows.Forms.PrintPreviewDialog> Leistung des für Netzwerkdrucker optimiert ist. Weitere Informationen finden Sie unter [PrintPreviewDialog-Steuerelementübersicht](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Steuert, ob Jahresbereichsprüfungen für japanische Kalenderlöschen erzwungen werden. `true`, um Jahresbereichsprüfungen `false` zu erzwingen und zu deaktivieren (Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Steuert, ob nur "1" als erstes Jahr einer japanischen Kalenderära in Analysevorgängen erkannt wird. `true`nur "1" zu erkennen; `false` , um entweder "1" oder Gannen (das Standardverhalten) zu erkennen. Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Steuert, ob das erste Jahr einer japanischen Kalenderära in Formatierungsvorgängen als "1" oder Gannen dargestellt wird. `true`das erste Jahr der Ära als "1" zu formatieren; `false` , um es als Gannen zu formatieren (das Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Steuert, ob asynchrone Vorgänge nicht aus dem Kontext des aufrufenden Threads fließen. Weitere Informationen finden Sie unter [CurrentCulture und CurrentUICulture Flow across tasks](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Steuert, <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> ob die Methode versucht, den Anspruchstyp nur mit dem letzten DNS-Eintrag abzugleichen. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet.FindClaims-Methode](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Steuert, ob AuthorizationContext.Empty ein veränderbares Objekt zurückgeben soll.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Steuert, ob `MAX_PATH` Pfade, die länger als <xref:System.IO.PathTooLongException>(260 Zeichen) sind, eine auswerfen. Weitere Informationen finden Sie unter [Long Path Support](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Steuert, ob systemeigene Betriebssystemroutinen für <xref:System.IO.Compression.DeflateStream> die Dekomprimierung durch die Klasse verwendet werden. `false`, um systemeigene APIs zu verwenden; `true` , um <xref:System.IO.Compression.DeflateStream> die Implementierung zu verwenden.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Verwendet den umgekehrten\\Schrägstrich (" ") anstelle des Schrägstrichs ("/") als Pfadtrennzeichen in der <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> Eigenschaft. Weitere Informationen finden Sie [unter Mitigation: ZipArchiveEntry.FullName Path Separator](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Steuert, ob Betriebssystemausnahmen, die auf Hintergrundthreads ausgelöst werden, die mit <xref:System.IO.Ports.SerialPort> Streams erstellt wurden, den Prozess beenden.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Steuert, ob die Normalisierung des Legacypfads <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> verwendet wird und URI-Pfade von den und Methoden unterstützt werden. Weitere Informationen finden Sie [unter Mitigation: Path Normalization](../../../migration-guide/mitigation-path-normalization.md) and [Mitigation: Path Colon Checks](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Steuert, ob ein Gleichheitstest die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> Eigenschaft <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> eines Objekts mit der Eigenschaft des zweiten Objekts vergleicht. Weitere Informationen finden Sie unter [Falsche Implementierung von MemberDescriptor.Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deaktiviert die Bestätigung der Bestätigung der Zertifikatserweiterten Schlüsselverwendung (EKU) (OID). Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deaktiviert TLS1.0 Browser Exploit Against SSL/TLS (BEAST) Mitigation durch Deaktivieren der Verwendung von SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Steuert, <xref:System.Net.ServicePointManager?displayProperty=nameWithType> ob <xref:System.Net.Security.SslStream?displayProperty=nameWithType> die und-Klassen das SSL 3.0-Protokoll verwenden können. Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deaktiviert SystemDefault TLS-Versionen, die auf den Standardwert tls12, Tls11, Tls zurückgesetzt werden.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deaktiviert sslStream TLS-Server-seitige Warnungen.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Steuert, ob ByRef SafeArray-Parameter für COM-Interop-Ereignisse wieder zu systemeigenem Code (`false`) marshallen oder ob das Zurückallieren in systemeigenen Code deaktiviert ist (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Steuert, ob [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) einige Steuerzeichen basierend auf den ECMAScript V6- und V8-Standards serialisiert. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Steuert, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ob der mehrere Anpassungen oder nur eine einzelne Anpassung für eine Zeitzone unterstützt. Wenn `true`, verwendet <xref:System.TimeZoneInfo> es den Typ, um Datums- und Uhrzeitdaten zu serialisieren und zu deserialisieren. Andernfalls wird der <xref:System.TimeZone> Typ verwendet, der keine mehrfachen Anpassungsregeln unterstützt.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Steuert, <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> ob eine größere Arraygröße während der Objektserialisierung und Deserialisierung verwendet wird. Legen Sie `true` diesen Schalter fest, um die Leistung der Serialisierung und <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>Deserialisierung großer Objektdiagramme nach Typen wie zu verbessern. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Steuert, <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29> ob der Konstruktor die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> Eigenschaft des neuen Objekts mit einem vorhandenen Objektverweis festlegt. Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Steuert, ob der Versuch, einen <xref:System.Security.Cryptography.AesCryptoServiceProvider> <xref:System.Security.Cryptography.CryptographicException>decryptor wiederzuverwenden, eine auslöst. Weitere Informationen finden Sie unter [AesCryptoServiceProvider decryptor bietet eine wiederverwendbare Transformation](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Steuert, ob der Wert der [CspParameters.ParentWindowHandle-Eigenschaft](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) ein [IntPtr ist,](xref:System.IntPtr) der die Speicherposition eines Fensterhandles darstellt, oder ob es sich um ein Fensterhandle (ein HWND) handelt. Weitere Informationen finden Sie unter [Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Steuert, ob die Verwendung von verwalteten Kryptografieklassen im FIPS-Modus eine <xref:System.Security.Cryptography.CryptographicException> (`true`) oder auf die Implementierung von Systembibliotheken (`false`) basiert.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob die Standardeinstellung für einige SignedCMS-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Steuert, <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> ob die Methode alle benannten Kurven,`false`die vom Betriebssystem unterstützt werden , korrekt verarbeitet oder auf das Ältere Verhalten zurückgesetzt wird.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedXML-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Bestimmt, `TransportWithMessageCredential` ob der Sicherheitsmodus Nachrichten mit einem nicht signierten "to"-Header zulässt. Dies ist ein Opt-in-Schalter. Weitere Informationen finden Sie [unter Laufzeitänderungen in .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Steuert, <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> ob der <xref:System.ArgumentException> Konstruktor eine auslöst, wenn eines der Elemente `null`ist.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Bestimmt, ob der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicheranbieter zu verwenden, eine Ausnahme auslöst. Weitere Informationen finden Sie unter [WCF-Transportsicherheit unterstützt Zertifikate, die mit CNG gespeichert sind.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Wenn Sie den HTTP-Transport mit einem selbst `true` gehosteten Dienst verwenden, wird `Connection: close` dieser Wert so eingestellt, dass WCF eine Anwendung ignoriert, die den Header zu den Antwortheadern für eine Anforderung hinzufügt. Festlegen dieses `false` Werts `Connection: close` auf das Hinzufügen des Headers zu den Antwortheadern, was dazu führt, dass der Anforderungssocket geschlossen wird, nachdem eine Antwort gesendet wurde.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Behandelt Deadlocks, die sich aus dem Einschränken von Instanzen eines Wiedereinstiegsdienstes auf einen einzelnen Ausführungsthread ergeben.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Zusammen `Switch.System.Net.DontEnableSchUseStrongCrypto`mit bestimmt, ob die WCF-Nachrichtensicherheit TLS 1.1 und TLS 1.2 verwendet.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Der Wert `false` von legt die Standardkonfiguration fest, damit das Betriebssystem das Protokoll auswählen kann. Der Wert `true` von legt den Standardwert auf das höchste verfügbare Protokoll fest. (Auch auf Service-Zweig früherer Framework-Versionen verfügbar)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Bestimmt, ob der Standardmäßige Nachrichtensignaturalgorithmus für MSMQ-Nachrichten in WCF SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Steuert, ob WCF einen SHA1- oder einen SHA256-Hash verwendet, um zufällige Namen für benannte Pipes zu generieren.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Steuert, ob eine [NullReferenceException](xref:System.NullReferenceException) ausgelöst werden soll, wenn die Ausnahmenachricht null ist.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Steuert, ob Beim Dienststart ausgelöste Ausnahmen an den <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> Aufrufer der Methode weitergegeben werden.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Steuert, <xref:System.Threading.Timer> ob Instances Leistungsverbesserungen für Umgebungen mit hoher Skalierung nutzen. Wenn `true`, sind die Leistungsverbesserungen aktiviert. wenn `false` (der Standardwert), sind sie deaktiviert.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Legt fest, ob bestimmte prozentig codierte Zeichen, die manchmal dekodiert wurden, nun konsistent codiert bleiben. Wenn `true`, werden sie decodiert; andernfalls `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Bestimmt die Behandlung von Unicode-Bidirektionalzeichen in URIs. `true`, um sie von DEN URIs zu entfernen; `false` , um sie zu bewahren und prozentig zu kodieren.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Bestimmt, ob Windows Presentation Foundation`true`einen alten Algorithmus`false`( ) oder \*einen neuen Algorithmus ( ) beim Zuweisen von Speicherplatz zu -Spalten anwendet. Weitere Informationen finden Sie unter [Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Steuert, ob ein Selektor oder ein Registerkartensteuerelement immer den Wert der ausgewählten Werteigenschaft aktualisiert, bevor das Änderungsereignis der Auswahl angezeigt wird.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Legt fest, ob nicht Adorner-basiertes <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.PasswordBox> Auswahlrendering für die und`false`Steuerelemente verfügbar ist, um okkluden`true`Text ( zu verhindern", oder ob Text nur in der Adorner-Ebene ( ) gerendert wird.|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Steuert, ob benutzerdefinierte IList-Indexer`true`von der <xref:System.Windows.Data.Binding?displayProperty=nameWithType> `false`Klasse falsch ( ) oder korrekt ( ) verwendet werden.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Bestimmt, ob DPI-Änderungen pro System (wert ) `false`oder pro Monitor `true`(Wert von ) auftreten.|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Steuert, ob Verbesserungen bei der <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> Größenänderung von Steuerelementen in einem,`true`wenn WPF`false`im modusfürstfreundlichen Modus pro Monitor ausgeführt wird, deaktiviert ( ) oder aktiviert sind ( ).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Bestimmt, ob der Entwickler <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> die Aktion speziell behandeln muss, wenn Steuerelementtext vorhanden ist. `true`, um <xref:System.Windows.Forms.DomainUpDown.UpButton> die Aktion zu behandeln; `false` und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> Aktionen ordnungsgemäß synchronisiert <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> werden.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Optaus iert aus dem Code, der es einer benutzerdefinierten <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> Implementierung ermöglicht, Nachrichten sicher zu filtern, ohne eine Ausnahme auszulösen, wenn die Methode aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Bestimmt, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> ob die Eigenschaft das Quellcodesteuerelement zurückgibt, <xref:System.Windows.Forms.ToolStripMenuItem> wenn der Benutzer das Menü von einem verschachtelten Steuerelement aus öffnet. `true`, `null`um das Legacy-Verhalten zurückzugeben; `false` , um das Quellcodeverwaltung zurückzugeben.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Steuert, ob die Unterstützung für`true`QuickInfo-Aufrufe deaktiviert ( ) oder aktiviert ist (`false`). Das Aktivieren der Unterstützung für QuickInfo-Aufrufe `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2`erfordert `Switch.UseLegacyAccessibilityFeatures.3` auch legacy Accessibility-Features, die durch definiert sind, und alle sind deaktiviert (auf festgelegt). `false`|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Bestimmt, ob `WM_POINTER`ein optionaler -basierter Touch/Stylus-Stack in WPF-Anwendungen aktiviert ist. Weitere Informationen finden Sie [unter Mitigation: Pointer-based Touch and Stylus Support](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Bestimmt, ob der für Prüfsummen verwendete Standardhashalgorithmus`false`SHA256`true`( ) oder SHA1 ( ) ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Steuert, ob eine ältere [NullReferenceException](xref:System.NullReferenceException) anstelle der Ausnahme ausgelöst wird, die genauer auf die Ursache der Ausnahme hinweist (z. B. eine [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) oder eine [FileNotFoundException](xref:System.IO.FileNotFoundException). Es ist für die Verwendung durch Code vorgesehen, der von der Behandlung der [NullReferenceException](xref:System.NullReferenceException)abhängt. | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Steuert, ob das Prüfsummen-Hashen von XOML-Dateien`true`in Workflowprojektbuilds den MD5-Algorithmus ( ) verwendet oder ob sie den SHA256-Algorithmus verwenden, der als Standard in .NET Framework 4.8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Steuert, ob die Prüfsummen-Hashung durch den`true`SqlTrackingService den MD5-Algorithmus ( ) für zwischengespeicherte Zeichenfolgen verwendet oder ob der SHA256-Algorithmus als Standard in .NET Framework 4.8 eingeführt wird.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Steuert, ob die Prüfsummen-Hashung durch die`true`Workflow-Runtime den MD5-Algorithmus ( ) für zwischengespeicherte Workflowdefinitionen verwendet oder ob der SHA256-Algorithmus verwendet wird, der in .NET Framework 4.8 als Standard eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Steuert, ob Barrierefreiheitsfeatures, die ab .NET Framework 4.7.1 verfügbar sind, aktiviert oder deaktiviert sind. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Steuert, ob in .NET Framework 4.7.2`false`verfügbare Eingabehilfen`true`aktiviert ( ) oder deaktiviert sind ( ). Wenn `true` `Switch.UseLegacyAccessibilityFeatures` , muss `true` auch die Eingabehilfen von .NET Framework 4.7.1 aktiviert werden.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Steuert, ob in .NET Framework 4.8`false`eingeführte Eingabehilfen aktiviert ( ) oder deaktiviert sind (`true`). Wenn `true` `Switch.UseLegacyAccessibilityFeatures` , `Switch.UseLegacyAccessibilityFeatures.2` und `true`muss auch sein .|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Steuert, ob QuickInfos angezeigt werden, wenn ein Benutzer den`true`Mauszeiger über ein WPF-Steuerelement ( )`false`zeigt, oder ob sie sowohl auf der Tastaturfokus als auch über die Tastenkombination ( , das Standardverhalten) angezeigt werden. Für Anwendungen, die auf .NET Framework 4.8 ausgeführt werden, aber auf frühere Versionen `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2`von `Switch.UseLegacyAccessibilityFeatures.3` .NET Framework `false`abzielen, erfordert die Aktivierung sowohl der Tastaturfokus- als auch der Tastenkombinationsunterstützung , und alle sind auf festgelegt.|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Steuert, ob leere Schlüsselsequenzen in zusammengesetzten Schlüsseln von der XSD-Schemaüberprüfung ignoriert werden. Weitere Informationen finden Sie [unter Mitigation: XML Schema Validation](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> Anstatt einer `AppContextSwitchOverrides` Anwendungskonfigurationsdatei ein Element hinzuzufügen, können Sie die Switches `static` auch programmgesteuert festlegen, indem Sie die Methode (in C) oder `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> aufrufen.

 Bibliotheksentwickler können auch benutzerdefinierte Switches definieren, damit Aufrufer die geänderten Funktionen, die in späteren Versionen ihrer Bibliotheken eingeführt wurden, deaktivieren können. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.AppContext>-Klasse.

## <a name="switches-in-aspnet-apps"></a>Switches in ASP.NET Apps

Sie können eine ASP.NET-Anwendung so konfigurieren, dass Kompatibilitätseinstellungen verwendet werden, indem Sie dem [ \<](../appsettings/index.md) Abschnitt appSettings>Abschnitt der Datei web.config ein [ \<Element ">hinzufügen"](../appsettings/add-element-for-appsettings.md) hinzufügen.

Im folgenden Beispiel `<add>` wird das Element `<appSettings>` verwendet, um dem Abschnitt einer web.config-Datei zwei Einstellungen hinzuzufügen:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Beispiel

 Im folgenden Beispiel `AppContextSwitchOverrides` wird das Element zum Definieren `Switch.System.Globalization.NoAsyncCurrentCulture`eines einzelnen Anwendungskompatibilitätsschalters verwendet, der verhindert, dass Kultur in asynchronen Methodenaufrufen über Threads hinweg fließt.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 Im folgenden Beispiel `AppContextSwitchOverrides` wird das Element verwendet, `Switch.System.Globalization.NoAsyncCurrentCulture` `Switch.System.IO.BlockLongPaths`um zwei Anwendungskompatibilitätsschalter zu definieren, und . Ein Semikolon trennt die beiden Namen/Wert-Paare.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Abschwächen neuer Verhaltensweisen in .NET Framework 4.6 und höher](../../../migration-guide/mitigations.md)
- <xref:System.AppContext?displayProperty=nameWithType>
- [\<Laufzeit> Element](runtime-element.md)
- [\<Konfiguration> Element](../configuration-element.md)
