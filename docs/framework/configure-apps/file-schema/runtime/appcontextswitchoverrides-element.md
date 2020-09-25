---
title: Appcontex\witchoverrides-Element
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: ab74886edcc86c900c56017867a3b81c9cb7886e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176148"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides>-Element

Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<AppContextSwitchOverrides>**

## <a name="syntax"></a>Syntax

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|Beschreibung|
|---------------|-----------------|
|`value`|Erforderliches Attribut.<br /><br /> Definiert einen oder mehrere Switchnamen und die zugehörigen booleschen Werte.|

### <a name="value-attribute"></a>value-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|"Name = Wert"|Ein vordefinierter SwitchName zusammen mit dem Wert ( `true` oder `false` ). Mehrere Switch-Name-Wert-Paare werden durch Semikolons (";") getrennt. Eine Liste der vordefinierten Switchnamen, die von der .NET Framework unterstützt werden, finden Sie im Abschnitt "Hinweise".|

### <a name="child-elements"></a>Untergeordnete Elemente

 Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|

## <a name="remarks"></a>Bemerkungen

 Ab .NET Framework 4,6 ermöglicht das- `<AppContextSwitchOverrides>` Element in einer Konfigurationsdatei Aufrufern einer API, zu bestimmen, ob Ihre APP neue Funktionen nutzen oder die Kompatibilität mit früheren Versionen einer Bibliothek beibehalten kann. Wenn sich z. b. das Verhalten einer API zwischen zwei Versionen einer Bibliothek geändert hat, ermöglicht das- `<AppContextSwitchOverrides>` Element Aufrufern von dieser API, das neue Verhalten bei Versionen der Bibliothek zu abonnieren, die die neue Funktionalität unterstützen. Für apps, die APIs im .NET Framework aufzurufen, `<AppContextSwitchOverrides>` kann das-Element auch Aufrufern ermöglichen, deren apps auf eine frühere Version des .NET Framework abzielen, um neue Funktionen zu abonnieren, wenn Ihre APP in einer Version des .NET Framework ausgeführt wird, das diese Funktion enthält.

 Das- `value` Attribut des- `<AppContextSwitchOverrides>` Elements besteht aus einer einzelnen Zeichenfolge, die aus einem oder mehreren durch Semikolons getrennten Name/Wert-Paaren besteht.  Jeder Name identifiziert einen Kompatibilitäts Schalter, und der entsprechende Wert ist ein boolescher Wert ( `true` oder `false` ), der angibt, ob der Switch festgelegt ist. Standardmäßig ist der Schalter `false` , und Bibliotheken stellen die neue Funktionalität bereit. Sie stellen nur die vorherige Funktionalität bereit, wenn der Switch festgelegt ist (d. h. sein Wert ist `true` ). Dadurch können Bibliotheken neues Verhalten für eine vorhandene API bereitstellen, während Aufrufer, die vom vorherigen Verhalten abhängen, die neue Funktionalität ablehnen können.

.NET Framework unterstützt die folgenden Schalter:

|SwitchName|Beschreibung|Eingeführt|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Steuert, ob Windows Presentation Foundation einen Legacy Algorithmus für das Steuerelement Layout verwendet. Weitere Informationen finden Sie unter [Entschärfung: WPF-Layout](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Steuert, ob der Standard Algorithmus, der zum Signieren von Paket Teilen von PackageDigitalSignatureManager verwendet wird, SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Wenn diese Einstellung auf festgelegt `false` ist, wird das Debuggen von XAML-basierten Workflow Projekten mit Visual Studio ermöglicht, wenn "PPS" aktiviert Ohne diese wird eine <xref:System.NullReferenceException> in Aufrufen von Methoden in der System. Activities-Assembly ausgelöst.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Steuert, ob die Prüfsumme für eine Workflow Instanz im Debugger MD5 oder SHA1 verwendet. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Steuert, ob das hashup der Workflow Prüf Summe den SHA1-Algorithmus verwendet, der in .NET Framework 4,7 () als Standard eingeführt `true` wurde, oder ob der standardmäßige SHA256-Algorithmus verwendet wird, der als Standardwert in .NET Framework 4,8 () eingeführt wurde `false` .<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Steuert, ob Stapel Überwachungen bei der Verwendung portabler pdsb-Informationen Quelldatei-und Zeilen Informationen enthalten können. `false` So schließen Sie Quelldatei-und Zeilen Informationen ein andernfalls `true` .|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Steuert, ob die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> Methode eine Ausnahme auslöst, wenn ein <xref:System.Drawing.Icon> Objekt über PNG-Frames verfügt. Weitere Informationen finden Sie unter [Entschärfung: PNG-Bilder in Symbolobjekten](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Bestimmt <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> , ob Objekte ordnungsgemäß verworfen werden, wenn Sie von der-Methode der-Auflistung hinzugefügt werden <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> . `true` So behalten Sie das Legacy Verhalten bei `false` , um alle privaten Schriftart Objekte zu verwerfen. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Steuert, ob die Leistung von <xref:System.Windows.Forms.PrintPreviewDialog> für Netzwerkdrucker optimiert ist. Weitere Informationen finden Sie unter [Übersicht über das PrintPreviewDialog-Steuer](/dotnet/desktop/winforms/controls/printpreviewdialog-control-overview-windows-forms)Element.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Steuert, ob Jahres Bereichs Prüfungen für japanische Kalender Zeiträume erzwungen werden. `true` zum Erzwingen von Überprüfungen im Jahres Bereich und `false` zum Deaktivieren der Werte (Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Steuert, ob nur "1" als das erste Jahr eines japanischen Kalender Zeitraums bei der Ausführung von Diagnose Vorgängen erkannt wird. `true` , wenn nur "1" erkannt werden soll. `false` um entweder "1" oder "Gannen" (Standardverhalten) zu erkennen. Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Steuert, ob das erste Jahr eines japanischen Kalender Zeitraums in Formatierungs Vorgängen als "1" oder "Gannen" dargestellt wird. `true` , wenn das erste Jahr des Jahrs als "1" formatiert werden soll. `false` zum Formatieren als Gannen (Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Steuert, ob asynchrone Vorgänge nicht aus dem Kontext des aufrufenden Threads abgeleitet werden. Weitere Informationen finden Sie unter [CurrentCulture und CurrentUICulture Flow over Tasks](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Steuert, ob die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> Methode versucht, den Anspruchstyp nur mit dem letzten DNS-Eintrag zu vergleichen. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet.FindClaims-Methode](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Steuert, ob AuthorizationContext. Empty ein änderbares Objekt zurückgeben darf.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Steuert, ob Pfade, die länger sind als `MAX_PATH` (260 Zeichen), eine auslösen <xref:System.IO.PathTooLongException> . Weitere Informationen finden Sie [unter Unterstützung für lange Pfade](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Steuert, ob systemeigene Betriebssystem Routinen zur Dekomprimierung durch die-Klasse verwendet werden <xref:System.IO.Compression.DeflateStream> . `false` So verwenden Sie Native APIs `true` , um die-Implementierung zu verwenden <xref:System.IO.Compression.DeflateStream> .|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Verwendet den umgekehrten Schrägstrich (" \\ ") anstelle des Schrägstrichs ("/") als Pfad Trennzeichen in der- <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> Eigenschaft. Weitere Informationen finden Sie unter  [Entschärfung: zizichiveentry. FullName Pfad Trennzeichen](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Steuert, ob die Betriebssystem Ausnahmen, die bei mit Streams erstellten Hintergrundthreads ausgelöst werden, <xref:System.IO.Ports.SerialPort> den Prozess beenden.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Steuert, ob die Normalisierung des Legacy Pfades verwendet wird und URI-Pfade von den Methoden und unterstützt werden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> . Weitere Informationen finden Sie unter [Entschärfung: Pfad Normalisierung](../../../migration-guide/mitigation-path-normalization.md) und [Entschärfung: Pfad-Doppelpunkt Überprüfungen](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Steuert, ob ein Test auf Gleichheit die- <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> Eigenschaft eines Objekts mit der- <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> Eigenschaft des zweiten Objekts vergleicht. Weitere Informationen finden Sie unter [falsche Implementierung von mitglieddeskriptor.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)ist ist.|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deaktiviert die Überprüfung der EKU-Objekt Kennung (Enhanced Key Usage, EKU) des Zertifikats. Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deaktiviert den TLS 1.0-Browser Exploit gegen SSL/TLS (Beast) Entschärfung durch Deaktivierung der Verwendung von SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Steuert, ob die <xref:System.Net.ServicePointManager?displayProperty=nameWithType> - <xref:System.Net.Security.SslStream?displayProperty=nameWithType> Klasse und die-Klasse das SSL 3,0-Protokoll verwenden können. Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deaktiviert die System default-TLS-Versionen, die auf den Standardwert von Tls12, Tls11, TLS zurückgesetzt werden.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deaktiviert serverseitige SslStream-TLS-Warnungen.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Steuert, ob ByRef SAFEARRAY-Parameter für COM-Interop-Ereignisse zurück in systemeigenen Code ( `false` ) oder ob das Marshalling zurück zu nativem Code deaktiviert ist ( `true` ).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Steuert, ob [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) einige Steuerzeichen basierend auf den ECMAScript V6-und V8-Standards serialisiert. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Steuert, ob der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> mehrere Anpassungen oder nur eine einzelne Anpassung für eine Zeitzone unterstützt. Wenn `true` , wird der <xref:System.TimeZoneInfo> -Typ zum Serialisieren und Deserialisieren von Datums-und Uhrzeitdaten verwendet; andernfalls wird der- <xref:System.TimeZone> Typ verwendet, der mehrere Anpassungsregeln nicht unterstützt.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Steuert, ob <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> bei der Objektserialisierung und-Deserialisierung eine größere Array Größe verwendet wird. Legen Sie diesen Schalter auf fest `true` , um die Leistung der Serialisierung und Deserialisierung von großen Objekt Diagrammen nach Typen wie zu verbessern <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> . |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Steuert, ob der <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29> Konstruktor die-Eigenschaft des neuen Objekts <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> mit einem vorhandenen Objekt Verweis festlegt. Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Steuert, ob der Versuch, eine <xref:System.Security.Cryptography.AesCryptoServiceProvider> Entschlüsselungen wiederzuverwenden, eine auslöst <xref:System.Security.Cryptography.CryptographicException> . Weitere Informationen finden Sie unter [AesCryptoServiceProvider Entschlüsselungs stellt eine wiederverwendbare Transformation bereit](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Steuert, ob der Wert der [CspParameters. Parameter WindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) -Eigenschaft ein [IntPtr](xref:System.IntPtr) ist, das die Speicherposition eines Fenster Handles darstellt, oder ob es sich um ein Fenster Handle (HWND) handelt. Weitere Informationen finden Sie unter [Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Steuert, ob durch die Verwendung verwalteter Kryptografieklassen im-PPS-Modus ein <xref:System.Security.Cryptography.CryptographicException> ( `true` ) oder die Implementierung von Systembibliotheken () ausgelöst wird `false` .|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedCms-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Steuert, ob die <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> Methode alle benannten Kurven, die vom Betriebssystem unterstützt werden (), ordnungsgemäß verarbeitet `false` oder auf das Legacy Verhalten zurückgesetzt wird.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedXml-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Bestimmt, ob der `TransportWithMessageCredential` Sicherheitsmodus Nachrichten mit einem unsignierten "to"-Header zulässt. Dies ist ein Opt-in-Switch. Weitere Informationen finden Sie unter [Lauf Zeit Änderungen in der .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Steuert, ob der <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> Konstruktor eine auslöst, <xref:System.ArgumentException> Wenn eines der Elemente ist `null` .|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Bestimmt, ob der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicher Anbieter zu verwenden, eine Ausnahme auslöst. Weitere Informationen finden [Sie unter WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe von CNG gespeichert](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)wurden.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Wenn Sie den HTTP-Transport mit einem selbstgeh osteten Dienst verwenden, bewirkt das Festlegen dieses Werts auf, `true` dass WCF eine Anwendung ignoriert, die dem `Connection: close` Antwortheader für eine Anforderung den-Header hinzufügt. Wenn Sie diesen Wert auf festlegen `false` , kann der- `Connection: close` Header den Antwort Headern hinzugefügt werden, was dazu führt, dass der Anforderungs Socket geschlossen wird, nachdem eine Antwort gesendet wurde.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Behandelt Deadlocks, die sich aus der Einschränkung von Instanzen eines Eintritts inderanten dienstanzen auf einen einzelnen Ausführungs Thread ergeben.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Bestimmt zusammen mit `Switch.System.Net.DontEnableSchUseStrongCrypto` , ob die WCF-Nachrichten Sicherheit TLS 1,1 und TLS 1,2 verwendet.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Der Wert `false` legt die Standardkonfiguration fest, um dem Betriebssystem das Auswählen des Protokolls zu ermöglichen. Der Wert `true` legt den Standardwert auf das höchste verfügbare Protokoll fest. (Auch für den Wartungs Zweig früherer Frameworkversionen verfügbar)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Bestimmt, ob der standardmäßige Nachrichten Signatur Algorithmus für MSMQ-Nachrichten in WCF SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Steuert, ob WCF einen SHA1-oder einen SHA256-Hash verwendet, um zufällige Namen für Named Pipes zu generieren.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Steuert, ob eine [NullReferenceException](xref:System.NullReferenceException) ausgelöst werden soll, wenn die Ausnahme Meldung NULL ist.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Steuert, ob für den Dienst Start ausgelöste Ausnahmen an den Aufrufer der-Methode weitergegeben werden <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> .|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Steuert, ob <xref:System.Threading.Timer> Instanzen Leistungsverbesserungen für hochskalierbare Umgebungen nutzen. Wenn `true` der Wert ist, werden die Leistungsverbesserungen aktiviert; Wenn `false` (der Standardwert), werden diese deaktiviert.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Bestimmt, ob bestimmte Prozent codierte Zeichen, die manchmal decodiert waren, jetzt konsistent Links codiert sind. `true`Gibt an, dass Sie decodiert werden, andernfalls `false` .|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Bestimmt die Handhabung von bidirektionalen Unicode-Zeichen in URIs. `true` , um Sie aus URIs zu entfernen. `false` , um Sie beizubehalten und zu codieren.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Bestimmt, ob Windows Presentation Foundation einen alten Algorithmus ( `true` ) oder einen neuen Algorithmus ( `false` ) zum Zuordnen von Speicherplatz für \* -Spalten anwendet. Weitere Informationen finden Sie unter [Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Steuert, ob ein Selector-Steuerelement oder ein Registerkarten-Steuerelement den Wert der ausgewählten Wert Eigenschaft immer aktualisiert, bevor das Auswahl Änderungs Ereignis erhöht wird.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Bestimmt, ob nicht-Adorner-basiertes Auswahl Rendering für das-Steuerelement und das-Steuerelement verfügbar ist, <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.PasswordBox> um den okdierten Text () zu verhindern `false` , oder ob Text nur in der Adornerebene () gerendert wird `true` .|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Steuert, ob benutzerdefinierte IList-Indexer falsch ( `true` ) oder ordnungsgemäß ( `false` ) von der-Klasse verwendet werden <xref:System.Windows.Data.Binding?displayProperty=nameWithType> .|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Bestimmt, ob dpi-Änderungen auf einem pro-System-(Wert `false` ) oder pro Monitor (Wert `true` ) erfolgen.|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Steuert, ob Verbesserungen bei der Größenänderung von Steuerelementen in einem, <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> Wenn WPF im Überwachungsmodus pro Monitor ausgeführt wird deaktiviert ( `true` ) oder aktiviert ( `false` ) ist.|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Bestimmt, ob der Entwickler die Aktion speziell verarbeiten muss, <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> Wenn der Steuerelement Text vorhanden ist. `true` , um die <xref:System.Windows.Forms.DomainUpDown.UpButton> Aktion zu verarbeiten,, `false` damit die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> Aktionen und ordnungsgemäß synchronisiert werden.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Beendet den Code, mit dem eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> Implementierung Nachrichten sicher filtern kann, ohne eine Ausnahme auszulösen, wenn die- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> Methode aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Bestimmt, ob die- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> Eigenschaft das Quell Steuerelement zurückgibt, wenn der Benutzer das Menü von einem-Steuerelement öffnet <xref:System.Windows.Forms.ToolStripMenuItem> . `true` , wenn `null` das Legacy Verhalten zurückgegeben werden soll,, `false` um die Quell Code Verwaltung zurückzugeben.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Steuert, ob die QuickInfo-Aufruf Unterstützung deaktiviert ( `true` ) oder aktiviert ( `false` ) ist. Das Aktivieren der Unterstützung von QuickInfo-aufrufen erfordert auch Legacy-Barrierefreiheits Funktionen `Switch.UseLegacyAccessibilityFeatures` , die von, `Switch.UseLegacyAccessibilityFeatures.2` und `Switch.UseLegacyAccessibilityFeatures.3` deaktiviert sind (auf festgelegt `false` ).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Bestimmt, ob `WM_POINTER` in WPF-Anwendungen ein optionaler,-basierter Fingerabdruck Stapel aktiviert ist. Weitere Informationen finden Sie [unter Entschärfung: Zeiger basierte Berührungs-und tablettstiftunterstützung](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md) .|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Bestimmt, ob der für Prüfsummen verwendete Standard Hash Algorithmus SHA256 ( `false` ) oder SHA1 ( `true` ) ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Steuert, ob eine Legacy- [NullReferenceException](xref:System.NullReferenceException) anstelle der Ausnahme ausgelöst wird, die die Ursache der Ausnahme genauer angibt (z. b. eine [directoriynotfoundexception](xref:System.IO.DirectoryNotFoundException) oder eine file [topics](xref:System.IO.FileNotFoundException)-Eigenschaft). Sie ist für die Verwendung durch Code vorgesehen, der von der Behandlung von [NullReferenceException](xref:System.NullReferenceException)abhängig ist. | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Steuert, ob die Prüfsummen Hashwerte von XOML-Dateien in Workflow Projektbuilds den MD5-Algorithmus ( `true` ) verwenden oder ob Sie den SHA256-Algorithmus verwenden, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Steuert, ob das Hash von Prüfsummen durch den SqlTrackingService den MD5-Algorithmus ( `true` ) für zwischengespeicherte Zeichen folgen verwendet oder ob der SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Steuert, ob ein Prüfsummen-Hashwert von der Workflow Laufzeit den MD5-Algorithmus ( `true` ) für zwischengespeicherte Workflow Definitionen verwendet oder ob der SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Steuert, ob Barrierefreiheits Funktionen, die mit .NET Framework 4.7.1 verfügbar sind, aktiviert oder deaktiviert sind. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Steuert, ob Barrierefreiheits Funktionen, die in .NET Framework 4.7.2 verfügbar sind, aktiviert ( `false` ) oder deaktiviert ( `true` ) sind. Wenn `true` , `Switch.UseLegacyAccessibilityFeatures` muss auch sein, `true` um .NET Framework 4.7.1-Barrierefreiheits Funktionen zu aktivieren.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Steuert, ob in .NET Framework 4,8 eingeführte Barrierefreiheits Features aktiviert ( `false` ) oder deaktiviert ( `true` ) sind. `true`, Wenn `Switch.UseLegacyAccessibilityFeatures` und `Switch.UseLegacyAccessibilityFeatures.2` ebenfalls sein müssen `true` .|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Steuert, ob Quick Infos angezeigt werden, wenn ein Benutzer mit dem Mauszeiger auf ein WPF-Steuerelement bewegt `true` wird () oder ob Sie sowohl auf dem Tastaturfokus als auch über die Tastenkombination ( `false` Standardverhalten) angezeigt werden. Bei Anwendungen, die auf .NET Framework 4,8 ausgeführt werden, aber auf frühere Versionen der .NET Framework abzielen, erfordert die Aktivierung von Tastaturfokus und Unterstützung von Tastenkombinationen, dass `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2` und `Switch.UseLegacyAccessibilityFeatures.3` alle auf festgelegt werden `false` .|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Steuert, ob leere schlüsselsequenzen in Verbund Schlüsseln durch die XSD-Schema Validierung ignoriert werden. Weitere Informationen finden Sie unter [Entschärfung: XML-Schema Validierung](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> Anstatt ein `AppContextSwitchOverrides` Element zu einer Anwendungs Konfigurationsdatei hinzuzufügen, können Sie die Schalter auch Programm gesteuert festlegen, indem Sie die- `static` Methode (in c#) oder die- `Shared` Methode (in Visual Basic) aufrufen <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> .

 Bibliotheks Entwickler können auch benutzerdefinierte Switches definieren, um Aufrufern zu ermöglichen, geänderte Funktionen zu abonnieren, die in späteren Versionen Ihrer Bibliotheken eingeführt wurden. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.AppContext>-Klasse.

## <a name="switches-in-aspnet-apps"></a>Switches in ASP.net-apps

Sie können eine ASP.NET-Anwendung so konfigurieren, dass Sie Kompatibilitäts Einstellungen verwendet, indem Sie [\<Add>](../appsettings/add-element-for-appsettings.md) dem- [\<appSettings>](../appsettings/index.md) Abschnitt der web.config Datei ein-Element hinzufügen.

Im folgenden Beispiel wird das- `<add>` Element verwendet, um dem- `<appSettings>` Abschnitt einer web.config Datei zwei Einstellungen hinzuzufügen:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird das-Element verwendet, `AppContextSwitchOverrides` um einen einzelnen Anwendungskompatibilitäts-Switch,, zu definieren, der `Switch.System.Globalization.NoAsyncCurrentCulture` verhindert, dass die Kultur bei asynchronen Methoden aufrufen in Threads fließt.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 Im folgenden Beispiel wird das `AppContextSwitchOverrides` -Element verwendet, um zwei Anwendungs Kompatibilitäts Switches und zu definieren `Switch.System.Globalization.NoAsyncCurrentCulture` `Switch.System.IO.BlockLongPaths` . Ein Semikolon trennt die beiden Name/Wert-Paare.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Migrieren von neuen Verhaltensweisen in .NET Framework 4.6 und höher](../../../migration-guide/mitigations.md)
- <xref:System.AppContext?displayProperty=nameWithType>
- [\<runtime>-Element](runtime-element.md)
- [\<configuration>-Element](../configuration-element.md)
