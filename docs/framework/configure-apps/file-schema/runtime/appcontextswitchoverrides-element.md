---
title: <AppContextSwitchOverrides>-Element
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fe354a929aad93ba4d4a6ea3cb43b2607be1f05
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252870"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContext witchoverrides-> Element
Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<AppContextSwitchOverrides>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut.<br /><br /> Definiert einen oder mehrere Switchnamen und die zugehörigen booleschen Werte.|  
  
### <a name="value-attribute"></a>value-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|"Name = Wert"|Ein vordefinierter SwitchName zusammen mit dem Wert`true` ( `false`oder). Mehrere Switch-Name-Wert-Paare werden durch Semikolons (";") getrennt. Eine Liste der vordefinierten Switchnamen, die von der .NET Framework unterstützt werden, finden Sie im Abschnitt "Hinweise".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit dem .NET Framework 4,6 ermöglicht das `<AppContextSwitchOverrides>` -Element in einer Konfigurationsdatei Aufrufern von einer API, um zu bestimmen, ob Ihre APP die neuen Funktionen nutzen oder die Kompatibilität mit früheren Versionen einer Bibliothek beibehalten kann. Wenn sich z. b. das Verhalten einer API zwischen zwei Versionen einer Bibliothek geändert hat, ermöglicht `<AppContextSwitchOverrides>` das-Element Aufrufern von dieser API, das neue Verhalten bei Versionen der Bibliothek zu abonnieren, die die neue Funktionalität unterstützen. Für apps, die APIs im .NET Framework aufzurufen, `<AppContextSwitchOverrides>` kann das-Element auch Aufrufern ermöglichen, deren apps auf eine frühere Version des .NET Framework abzielen, um neue Funktionen zu abonnieren, wenn Ihre APP in einer Version der .NET Framework ausgeführt wird, die Folgendes enthält: alitäts.  
  
 Das `value` -Attribut `<AppContextSwitchOverrides>` des-Elements besteht aus einer einzelnen Zeichenfolge, die aus einem oder mehreren durch Semikolons getrennten Name/Wert-Paaren besteht.  Jeder Name identifiziert einen Kompatibilitäts Schalter, und der entsprechende Wert ist ein boolescher`true` Wert `false`(oder), der angibt, ob der Switch festgelegt ist. Standardmäßig ist `false`der Schalter, und Bibliotheken stellen die neue Funktionalität bereit. Sie stellen nur die vorherige Funktionalität bereit, wenn der Switch festgelegt ist (d. h `true`. sein Wert ist). Dadurch können Bibliotheken neues Verhalten für eine vorhandene API bereitstellen, während Aufrufer, die vom vorherigen Verhalten abhängen, die neue Funktionalität ablehnen können.  
  
 Der .NET Framework unterstützt die folgenden Schalter:  
  
|SwitchName|Beschreibung|Aufgenommen|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Steuert, ob Windows Presentation Foundation einen Legacy Algorithmus für das Steuerelement Layout verwendet. Weitere Informationen finden Sie unter [Entschärfung: WPF-](../../../migration-guide/mitigation-wpf-layout.md)Layout.|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Steuert, ob der Standard Algorithmus, der zum Signieren von Paket Teilen von PackageDigitalSignatureManager verwendet wird, SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Wenn diese Einstellung `false`auf festgelegt ist, wird das Debuggen von XAML-basierten Workflow Projekten mit Visual Studio ermöglicht, wenn "PPS" aktiviert Ohne diese wird eine <xref:System.NullReferenceException> in Aufrufen von Methoden in der System. Activities-Assembly ausgelöst.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Steuert, ob die Prüfsumme für eine Workflow Instanz im Debugger MD5 oder SHA1 verwendet. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Steuert, ob das hashup der Workflow Prüf Summe den SHA1-Algorithmus verwendet, der in .NET Framework`true`4,7 () als Standard eingeführt wurde, oder ob der standardmäßige SHA256-Algorithmus verwendet wird`false`, der als Standardwert in .NET Framework 4,8 () eingeführt wurde.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Steuert, ob Stapel Überwachungen bei der Verwendung portabler pdsb-Informationen Quelldatei-und Zeilen Informationen enthalten können. `false`So schließen Sie Quelldatei-und Zeilen Informationen ein `true`andernfalls.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Steuert, ob <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> die Methode eine Ausnahme auslöst, <xref:System.Drawing.Icon> wenn ein Objekt über PNG-Frames verfügt. Weitere Informationen finden Sie unter [Entschärfung: PNG-Frames in Symbol](../../../migration-guide/mitigation-png-frames-in-icon-objects.md)Objekten.|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Bestimmt, <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> ob Objekte ordnungsgemäß verworfen werden, wenn Sie von der <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> -Methode der-Auflistung hinzugefügt werden. `true`So behalten Sie das Legacy Verhalten bei `false` , um alle privaten Schriftart Objekte zu verwerfen. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Steuert, ob die Leistung von <xref:System.Windows.Forms.PrintPreviewDialog> für Netzwerkdrucker optimiert ist. Weitere Informationen finden Sie unter [Übersicht über das PrintPreviewDialog-Steuer](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)Element.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Steuert, ob Jahres Bereichs Prüfungen für japanische Kalender Zeiträume erzwungen werden. `true`zum Erzwingen von Überprüfungen im Jahres `false` Bereich und zum Deaktivieren der Werte (Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Steuert, ob nur "1" als das erste Jahr eines japanischen Kalender Zeitraums bei der Ausführung von Diagnose Vorgängen erkannt wird. `true`, wenn nur "1" erkannt werden soll. `false` um entweder "1" oder "Gannen" (Standardverhalten) zu erkennen. Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6| 
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Steuert, ob das erste Jahr eines japanischen Kalender Zeitraums in Formatierungs Vorgängen als "1" oder "Gannen" dargestellt wird. `true`, wenn das erste Jahr des Jahrs als "1" formatiert werden soll. `false` zum Formatieren als Gannen (Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Steuert, ob asynchrone Vorgänge nicht aus dem Kontext des aufrufenden Threads abgeleitet werden. Weitere Informationen finden Sie unter [CurrentCulture und CurrentUICulture Flow over Tasks](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Steuert, ob <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> die Methode versucht, den Anspruchstyp nur mit dem letzten DNS-Eintrag zu vergleichen. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet. FindClaims-](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)Methode.|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Steuert, ob AuthorizationContext. Empty ein änderbares Objekt zurückgeben darf.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Steuert, ob Pfade, `MAX_PATH` die länger sind als (260 <xref:System.IO.PathTooLongException>Zeichen), eine auslösen. Weitere Informationen finden Sie [unter Unterstützung für lange Pfade](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Steuert, ob systemeigene Betriebssystem Routinen zur Dekomprimierung <xref:System.IO.Compression.DeflateStream> durch die-Klasse verwendet werden. `false`So verwenden Sie Native APIs , um die <xref:System.IO.Compression.DeflateStream> -Implementierung zu verwenden. `true`|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Verwendet den umgekehrten Schrägstrich (\\"") anstelle des Schrägstrichs ("/") als Pfad Trennzeichen in <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> der-Eigenschaft. Weitere Informationen finden [Sie unter Entschärfung: Zizichiveentry. FullName Pfad Trennzeichen](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Steuert, ob die Betriebssystem Ausnahmen, die bei mit <xref:System.IO.Ports.SerialPort> Streams erstellten Hintergrundthreads ausgelöst werden, den Prozess beenden.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Steuert, ob die Normalisierung des Legacy Pfades verwendet wird und URI-Pfade <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> von <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> den Methoden und unterstützt werden. Weitere Informationen finden Sie unter [Entschärfung: Normalisierung](../../../migration-guide/mitigation-path-normalization.md) und[Entschärfung des Pfades: Pfad-Doppel](../../../migration-guide/mitigation-path-colon-checks.md)Punkt Überprüfungen.|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Steuert, ob ein Test auf Gleichheit die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> -Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> -Eigenschaft des zweiten Objekts vergleicht. Weitere Informationen finden Sie unter [falsche Implementierung von mitglieddeskriptor.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)ist ist.|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deaktiviert die Überprüfung der EKU-Objekt Kennung (Enhanced Key Usage, EKU) des Zertifikats. Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deaktiviert den TLS 1.0-Browser Exploit gegen SSL/TLS (Beast) Entschärfung durch Deaktivierung der Verwendung von SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Steuert, ob <xref:System.Net.ServicePointManager?displayProperty=nameWithType> die <xref:System.Net.Security.SslStream?displayProperty=nameWithType> -Klasse und die-Klasse das SSL 3,0-Protokoll verwenden können. Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deaktiviert die System default-TLS-Versionen, die auf den Standardwert von Tls12, Tls11, TLS zurückgesetzt werden.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deaktiviert serverseitige SslStream-TLS-Warnungen.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Steuert, ob ByRef SAFEARRAY-Parameter für COM-Interop-Ereignisse zurück in`false`systemeigenen Code () oder ob das Marshalling zurück zu nativem Code deaktiviert ist (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Steuert, ob [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) einige Steuerzeichen basierend auf den ECMAScript V6-und V8-Standards serialisiert. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Steuert, ob <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> der mehrere Anpassungen oder nur eine einzelne Anpassung für eine Zeitzone unterstützt. Wenn `true`, wird der <xref:System.TimeZoneInfo> -Typ zum Serialisieren und Deserialisieren von Datums-und Uhrzeitdaten verwendet; andernfalls <xref:System.TimeZone> wird der-Typ verwendet, der mehrere Anpassungsregeln nicht unterstützt.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Steuert, <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> ob bei der Objektserialisierung und-Deserialisierung eine größere Array Größe verwendet wird. Legen Sie diesen Schalter `true` auf fest, um die Leistung der Serialisierung und Deserialisierung von großen Objekt Diagrammen nach Typen <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>wie zu verbessern. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Steuert, ob <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> der Konstruktor die- <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> Eigenschaft des neuen Objekts mit einem vorhandenen Objekt Verweis festlegt. Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](../../../migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Steuert, ob der Versuch, eine <xref:System.Security.Cryptography.AesCryptoServiceProvider> Entschlüsselungen wiederzuverwenden <xref:System.Security.Cryptography.CryptographicException>, eine auslöst. Weitere Informationen finden Sie unter [AesCryptoServiceProvider Entschlüsselungs stellt eine wiederverwendbare Transformation bereit](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Steuert, ob der Wert der [CspParameters. Parameter WindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) -Eigenschaft ein [IntPtr](xref:System.IntPtr) ist, das die Speicherposition eines Fenster Handles darstellt, oder ob es sich um ein Fenster Handle (HWND) handelt. Weitere Informationen finden Sie unter [Entschärfung: CspParameters. Parser WindowHandle erwartet ein HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Steuert, ob durch die Verwendung verwalteter Kryptografieklassen im-PPS`true`-Modus ein <xref:System.Security.Cryptography.CryptographicException> () oder die Implementierung von System`false`Bibliotheken () ausgelöst wird.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedCms-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Steuert, ob <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> die Methode alle benannten Kurven, die vom Betriebssystem unterstützt`false`werden (), ordnungsgemäß verarbeitet oder auf das Legacy Verhalten zurückgesetzt wird.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedXml-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Bestimmt, ob `TransportWithMessageCredential` der Sicherheitsmodus Nachrichten mit einem unsignierten "to"-Header zulässt. Dies ist ein Opt-in-Switch. Weitere Informationen finden Sie unter [Lauf Zeit Änderungen in der .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Steuert, ob <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> der Konstruktor eine <xref:System.ArgumentException> auslöst, wenn eines der Elemente `null`ist.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Bestimmt, ob der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicher Anbieter zu verwenden, eine Ausnahme auslöst. Weitere Informationen finden [Sie unter WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe von CNG gespeichert](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)wurden.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Wenn Sie den HTTP-Transport mit einem selbstgeh osteten Dienst verwenden, bewirkt `true` das Festlegen dieses Werts auf, dass WCF `Connection: close` eine Anwendung ignoriert, die dem Antwortheader für eine Anforderung den-Header hinzufügt. Wenn Sie diesen Wert `false` auf festlegen, `Connection: close` kann der-Header den Antwort Headern hinzugefügt werden, was dazu führt, dass der Anforderungs Socket geschlossen wird, nachdem eine Antwort gesendet wurde.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Behandelt Deadlocks, die sich aus der Einschränkung von Instanzen eines Wiedereintritts enden dienstanzen auf einen einzelnen Ausführungs Thread ergeben.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Bestimmt zusammen `Switch.System.Net.DontEnableSchUseStrongCrypto`mit, ob die WCF-Nachrichten Sicherheit TLS 1,1 und TLS 1,2 verwendet.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Der Wert `false` legt die Standardkonfiguration fest, um dem Betriebssystem das Auswählen des Protokolls zu ermöglichen. Der Wert `true` legt den Standardwert auf das höchste verfügbare Protokoll fest. (Auch für den Wartungs Zweig früherer Frameworkversionen verfügbar)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Bestimmt, ob der standardmäßige Nachrichten Signatur Algorithmus für MSMQ-Nachrichten in WCF SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Steuert, ob WCF einen SHA1-oder einen SHA256-Hash verwendet, um zufällige Namen für Named Pipes zu generieren.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Steuert, ob eine [NullReferenceException](xref:System.NullReferenceException) ausgelöst werden soll, wenn die Ausnahme Meldung NULL ist.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Steuert, ob für den Dienst Start ausgelöste Ausnahmen an den <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> Aufrufer der-Methode weitergegeben werden.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Steuert, <xref:System.Threading.Timer> ob Instanzen Leistungsverbesserungen für hochskalierbare Umgebungen nutzen. Wenn `true`der Wert ist, werden die Leistungsverbesserungen `false` aktiviert; wenn (der Standardwert), werden diese deaktiviert.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Bestimmt, ob bestimmte Prozent codierte Zeichen, die manchmal decodiert waren, jetzt konsistent Links codiert sind. Gibt an `false`, dass Sie decodiert werden, andernfalls. `true`|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Bestimmt die Handhabung von bidirektionalen Unicode-Zeichen in URIs. `true`, um Sie aus URIs zu entfernen. `false` , um Sie beizubehalten und zu codieren.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Bestimmt, ob Windows Presentation Foundation einen alten Algorithmus (`true`) oder einen neuen Algorithmus (`false`) zum Zuordnen von Speicher \*Platz für-Spalten anwendet. Weitere Informationen finden Sie unter [Entschärfung: Die Platz Zuordnung des Raster Steuer Elements zu Stern](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns)Spalten. |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Steuert, ob ein Selector-Steuerelement oder ein Registerkarten-Steuerelement den Wert der ausgewählten Wert Eigenschaft immer aktualisiert, bevor das Auswahl Änderungs Ereignis erhöht wird.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Bestimmt, ob nicht-Adorner-basiertes Auswahl Rendering für das <xref:System.Windows.Controls.TextBox> - <xref:System.Windows.Controls.PasswordBox> Steuerelement und das-Steuerelement`false`verfügbar ist, um den okdierten Text () zu verhindern, oder`true`ob Text nur in der Adornerebene () gerendert wird|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Steuert, ob benutzerdefinierte IList-Indexer falsch (`false`) oder ordnungsgemäß`true`() von <xref:System.Windows.Data.Binding?displayProperty=nameWithType> der-Klasse verwendet werden.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Bestimmt, ob dpi-Änderungen auf einem pro-System-(Wert `false`) oder pro Monitor ( `true`Wert) erfolgen.|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Steuert, ob Verbesserungen bei der Größen <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> Änderung von Steuerelementen in einem, wenn WPF im Überwachungsmodus pro`true`Monitor ausgeführt wird deaktiviert`false`() oder aktiviert () ist.|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Bestimmt, ob der Entwickler die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> Aktion speziell verarbeiten muss, wenn der Steuerelement Text vorhanden ist. `true`, wenn die <xref:System.Windows.Forms.DomainUpDown.UpButton> Aktion behandelt werden soll. damit die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> Aktionen und<xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> ordnungsgemäß synchronisiert werden. `false`|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Beendet den Code, mit dem eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> Implementierung Nachrichten sicher filtern kann, ohne eine Ausnahme auszulösen, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> -Methode aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter. PreFilterMessage](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)-Implementierungen.|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Bestimmt, ob <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> die-Eigenschaft das Quell Steuerelement zurückgibt, wenn der Benutzer das Menü <xref:System.Windows.Forms.ToolStripMenuItem> von einem-Steuerelement öffnet. `true`um zurück `null`zugeben, das Legacy Verhalten;. `false` , um die Quell Code Verwaltung zurückzugeben.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Steuert, ob die QuickInfo-Aufruf Unterstützung`true`deaktiviert () oder`false`aktiviert () ist. Das Aktivieren der Unterstützung von QuickInfo-aufrufen erfordert auch `Switch.UseLegacyAccessibilityFeatures`Legacy `Switch.UseLegacyAccessibilityFeatures.2`-Barrierefreiheits Funktionen, die von, `false`und `Switch.UseLegacyAccessibilityFeatures.3` deaktiviert sind (auf festgelegt).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Bestimmt, ob in `WM_POINTER`WPF-Anwendungen ein optionaler,-basierter Fingerabdruck Stapel aktiviert ist. Weitere Informationen finden Sie unter [Entschärfung: Zeiger basierte Unterstützung für Finger Eingaben und Tablettstift](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Bestimmt, ob der für Prüfsummen verwendete Standard Hash Algorithmus SHA256 (`false`) oder SHA1 (`true`) ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Steuert, ob eine Legacy- [NullReferenceException](xref:System.NullReferenceException) anstelle der Ausnahme ausgelöst wird, die die Ursache der Ausnahme genauer angibt (z. b. eine [directoriynotfoundexception](xref:System.IO.DirectoryNotFoundException) oder eine file [topics](xref:System.IO.FileNotFoundException)-Eigenschaft). Sie ist für die Verwendung durch Code vorgesehen, der von der Behandlung von [NullReferenceException](xref:System.NullReferenceException)abhängig ist. | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Steuert, ob die Prüfsummen Hashwerte von XOML-Dateien in Workflow Projektbuilds den MD5`true`-Algorithmus () verwenden oder ob Sie den SHA256-Algorithmus verwenden, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Steuert, ob das Hash von Prüfsummen durch den SqlTrackingService den MD5`true`-Algorithmus () für zwischengespeicherte Zeichen folgen verwendet oder ob der SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Steuert, ob ein Prüfsummen-Hashwert von der Workflow Laufzeit den MD5`true`-Algorithmus () für zwischengespeicherte Workflow Definitionen verwendet oder ob der SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Steuert, ob Barrierefreiheits Funktionen, die mit .NET Framework 4.7.1 verfügbar sind, aktiviert oder deaktiviert sind. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Steuert, ob Barrierefreiheits Funktionen, die in .NET Framework 4.7.2`false`verfügbar sind, aktiviert`true`() oder deaktiviert () sind. Wenn `true`, `Switch.UseLegacyAccessibilityFeatures` muss auch sein `true` , um .NET Framework 4.7.1-Barrierefreiheits Funktionen zu aktivieren.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Steuert, ob in .NET Framework 4,8 eingeführte Barrierefreiheits Features aktiviert`false`() oder deaktiviert`true`() sind. , `true` Wenn`Switch.UseLegacyAccessibilityFeatures` und ebenfalls`Switch.UseLegacyAccessibilityFeatures.2` sein`true`müssen.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Steuert, ob Quick Infos angezeigt werden, wenn ein Benutzer mit dem Mauszeiger auf ein WPF-`true`Steuerelement bewegt wird () oder ob Sie sowohl auf dem Tastaturfokus als auch über`false`die Tastenkombination (Standardverhalten) angezeigt werden. Bei Anwendungen, die auf .NET Framework 4,8 ausgeführt werden, aber auf frühere Versionen der .NET Framework abzielen, erfordert die Aktivierung von Tastaturfokus `Switch.UseLegacyAccessibilityFeatures`und Unterstützung `Switch.UseLegacyAccessibilityFeatures.3` von Tastenkombinationen, `false`dass `Switch.UseLegacyAccessibilityFeatures.2`und alle auf festgelegt werden.|.NET Framework 4.8|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Steuert, ob leere schlüsselsequenzen in Verbund Schlüsseln durch die XSD-Schema Validierung ignoriert werden. Weitere Informationen finden Sie unter [Entschärfung: XML-Schema](../../../migration-guide/mitigation-xml-schema-validation.md)Validierung.|.NET Framework 4.6|  
  
> [!NOTE]
> Anstatt ein `AppContextSwitchOverrides` Element zu einer Anwendungs Konfigurationsdatei hinzuzufügen, können Sie die Schalter auch Programm gesteuert festlegen, indem `static` Sie die C#-Methode `Shared` (in) oder <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> die-Methode (in Visual Basic) aufrufen.  
  
 Bibliotheks Entwickler können auch benutzerdefinierte Switches definieren, um Aufrufern zu ermöglichen, geänderte Funktionen zu abonnieren, die in späteren Versionen Ihrer Bibliotheken eingeführt wurden. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.AppContext>-Klasse.  
  
## <a name="switches-in-aspnet-applications"></a>Switches in ASP.NET-Anwendungen

Sie können eine ASP.NET-Anwendung so konfigurieren, dass Sie Kompatibilitäts Einstellungen verwendet, indem Sie dem [ \<Abschnitt appSettings >](../appsettings/index.md) der Datei "Web. config" ein [ \<Add >](../appsettings/add-element-for-appsettings.md) -Element hinzufügen. 

Im folgenden Beispiel wird das `<add>` -Element verwendet, um dem `<appSettings>` -Abschnitt einer Web. config-Datei zwei Einstellungen hinzuzufügen:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird das `AppContextSwitchOverrides` -Element verwendet, um einen einzelnen Anwendungskompatibilitäts-Switch, `Switch.System.Globalization.NoAsyncCurrentCulture`, zu definieren, der verhindert, dass die Kultur bei asynchronen Methoden aufrufen in Threads fließt.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 Im folgenden Beispiel wird `AppContextSwitchOverrides` `Switch.System.Globalization.NoAsyncCurrentCulture` das-Element verwendet, um zwei Anwendungs Kompatibilitäts `Switch.System.IO.BlockLongPaths`Switches und zu definieren. Beachten Sie, dass die beiden Name/Wert-Paare durch ein Semikolon getrennt werden.  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<Runtime-> Element](runtime-element.md)
- [\<configuration> Element](../configuration-element.md)
