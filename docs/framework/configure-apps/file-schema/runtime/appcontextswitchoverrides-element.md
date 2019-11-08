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
ms.openlocfilehash: 881b9fedfaa42ffb402e226a6b271f47feb20617
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736809"
---
# <a name="appcontextswitchoverrides-element"></a>\<appcontex\witchoverrides >-Element
Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<appcontex\witchoverrides >**  
  
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
|"Name = Wert"|Ein vordefinierter SwitchName zusammen mit dessen Wert (`true` oder `false`). Mehrere Switch-Name-Wert-Paare werden durch Semikolons (";") getrennt. Eine Liste der vordefinierten Switchnamen, die von der .NET Framework unterstützt werden, finden Sie im Abschnitt "Hinweise".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit dem .NET Framework 4,6 ermöglicht das `<AppContextSwitchOverrides>`-Element in einer Konfigurationsdatei Aufrufern einer API, um zu bestimmen, ob Ihre APP die neuen Funktionen nutzen oder die Kompatibilität mit früheren Versionen einer Bibliothek beibehalten kann. Wenn sich z. b. das Verhalten einer API zwischen zwei Versionen einer Bibliothek geändert hat, ermöglicht das `<AppContextSwitchOverrides>`-Element Aufrufern von dieser API, das neue Verhalten für Versionen der Bibliothek zu entscheiden, die die neue Funktionalität unterstützen. Für apps, die APIs im .NET Framework aufzurufen, kann das `<AppContextSwitchOverrides>`-Element auch Aufrufern zulassen, deren apps auf eine frühere Version des .NET Framework abzielen, um neue Funktionen zu abonnieren, wenn Ihre APP in einer Version der .NET Framework ausgeführt wird, die Folgendes enthält: alitäts.  
  
 Das `value`-Attribut des `<AppContextSwitchOverrides>`-Elements besteht aus einer einzelnen Zeichenfolge, die aus einem oder mehreren durch Semikolons getrennten Name/Wert-Paaren besteht.  Jeder Name identifiziert einen Kompatibilitäts Schalter, und der entsprechende Wert ist ein boolescher Wert (`true` oder `false`), der angibt, ob der Switch festgelegt ist. Standardmäßig ist der Schalter `false`, und Bibliotheken stellen die neue Funktionalität bereit. Sie stellen nur die vorherige Funktionalität bereit, wenn der Switch festgelegt ist (d. h., der Wert ist `true`). Dadurch können Bibliotheken neues Verhalten für eine vorhandene API bereitstellen, während Aufrufer, die vom vorherigen Verhalten abhängen, die neue Funktionalität ablehnen können.  
  
 Der .NET Framework unterstützt die folgenden Schalter:  
  
|SwitchName|Beschreibung|Aufgenommen|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Steuert, ob Windows Presentation Foundation einen Legacy Algorithmus für das Steuerelement Layout verwendet. Weitere Informationen finden Sie unter [Entschärfung: WPF-Layout](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Steuert, ob der Standard Algorithmus, der zum Signieren von Paket Teilen von PackageDigitalSignatureManager verwendet wird, SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Wenn diese Option auf `false`festgelegt ist, wird das Debuggen von XAML-basierten Workflow Projekten mit Visual Studio ermöglicht, wenn "fps" aktiviert Ohne diesen wird eine <xref:System.NullReferenceException> in Aufrufen von Methoden in der System. Activities-Assembly ausgelöst.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Steuert, ob die Prüfsumme für eine Workflow Instanz im Debugger MD5 oder SHA1 verwendet. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Steuert, ob das hashup der Workflow Prüf Summe den SHA1-Algorithmus verwendet, der als Standard in .NET Framework 4,7 (`true`) eingeführt wurde, oder ob der standardmäßige SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4,8 (`false`) eingeführt wurde.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Steuert, ob Stapel Überwachungen bei der Verwendung portabler pdsb-Informationen Quelldatei-und Zeilen Informationen enthalten können. `false`, um Quelldatei-und Zeilen Informationen einzubeziehen. Andernfalls `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Steuert, ob die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> Methode eine Ausnahme auslöst, wenn ein <xref:System.Drawing.Icon>-Objekt PNG-Frames aufweist. Weitere Informationen finden Sie unter [Entschärfung: PNG-Bilder in Symbolobjekten](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Bestimmt, ob <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType>-Objekte ordnungsgemäß verworfen werden, wenn Sie von der <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>-Methode der-Auflistung hinzugefügt werden `true`, um das Legacy Verhalten beizubehalten. `false`, alle privaten Schriftart Objekte zu verwerfen. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Steuert, ob die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> für Netzwerkdrucker optimiert ist. Weitere Informationen finden Sie unter [Übersicht über das PrintPreviewDialog-Steuer](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)Element.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Steuert, ob Jahres Bereichs Prüfungen für japanische Kalender Zeiträume erzwungen werden. `true`, um die Jahres Bereichs Überprüfung zu erzwingen und `false`, um Sie zu deaktivieren (das Standardverhalten). Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Steuert, ob nur "1" als das erste Jahr eines japanischen Kalender Zeitraums bei der Ausführung von Diagnose Vorgängen erkannt wird. `true`, nur "1" zu erkennen; `false`, um entweder "1" oder "Gannen" (Standardverhalten) zu erkennen. Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6| 
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Steuert, ob das erste Jahr eines japanischen Kalender Zeitraums in Formatierungs Vorgängen als "1" oder "Gannen" dargestellt wird. `true`, das erste Jahr für das ERA-Jahr als "1" zu formatieren. `false`, das Format als Gannen (Standardverhalten) zu formatieren. Weitere Informationen finden Sie unter [Arbeiten mit Kalendern](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Steuert, ob asynchrone Vorgänge nicht aus dem Kontext des aufrufenden Threads abgeleitet werden. Weitere Informationen finden Sie unter [CurrentCulture und CurrentUICulture Flow over Tasks](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Steuert, ob die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>-Methode versucht, den Anspruchstyp nur mit dem letzten DNS-Eintrag zu vergleichen. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet.FindClaims-Methode](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Steuert, ob AuthorizationContext. Empty ein änderbares Objekt zurückgeben darf.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Steuert, ob Pfade, die länger sind als `MAX_PATH` (260 Zeichen), eine <xref:System.IO.PathTooLongException>auslösen. Weitere Informationen finden Sie [unter Unterstützung für lange Pfade](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Steuert, ob systemeigene Betriebssystem Routinen für die Dekomprimierung durch die <xref:System.IO.Compression.DeflateStream>-Klasse verwendet werden. `false`, um Native APIs zu verwenden. `true`, die <xref:System.IO.Compression.DeflateStream>-Implementierung zu verwenden.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Verwendet den umgekehrten Schrägstrich ("\\") anstelle des Schrägstrichs ("/") als Pfad Trennzeichen in der <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>-Eigenschaft. Weitere Informationen finden Sie unter [Entschärfung: zizichiveentry. FullName Pfad Trennzeichen](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Steuert, ob die Betriebssystem Ausnahmen, die bei mit <xref:System.IO.Ports.SerialPort> Streams erstellten Hintergrundthreads ausgelöst werden, den Prozess beenden.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Steuert, ob die Normalisierung des Legacy Pfades verwendet wird und URI-Pfade von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> unterstützt werden. Weitere Informationen finden Sie unter [Entschärfung: Pfad Normalisierung](../../../migration-guide/mitigation-path-normalization.md) und [Entschärfung: Pfad-Doppelpunkt Überprüfungen](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Steuert, ob ein Test auf Gleichheit die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType>-Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType>-Eigenschaft des zweiten Objekts vergleicht. Weitere Informationen finden Sie unter [falsche Implementierung von mitglieddeskriptor.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)ist ist.|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deaktiviert die Überprüfung der EKU-Objekt Kennung (Enhanced Key Usage, EKU) des Zertifikats. Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deaktiviert den TLS 1.0-Browser Exploit gegen SSL/TLS (Beast) Entschärfung durch Deaktivierung der Verwendung von SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Steuert, ob die <xref:System.Net.ServicePointManager?displayProperty=nameWithType>-und <xref:System.Net.Security.SslStream?displayProperty=nameWithType> Klassen das SSL 3,0-Protokoll verwenden können. Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deaktiviert die System default-TLS-Versionen, die auf den Standardwert von Tls12, Tls11, TLS zurückgesetzt werden.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deaktiviert serverseitige SslStream-TLS-Warnungen.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Steuert, ob ByRef-SAFEARRAY-Parameter für COM-Interop-Ereignisse zurück in systemeigenen Code (`false`) oder ob das Marshalling zurück zu nativem Code deaktiviert ist (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Steuert, ob [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) einige Steuerzeichen basierend auf den ECMAScript V6-und V8-Standards serialisiert. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Steuert, ob der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> mehrere Anpassungen oder nur eine einzelne Anpassung für eine Zeitzone unterstützt. Wenn `true`, wird der <xref:System.TimeZoneInfo> Typ verwendet, um Datums-und Uhrzeit Daten zu serialisieren und zu deserialisieren. Andernfalls wird der <xref:System.TimeZone> Typ verwendet, der mehrere Anpassungsregeln nicht unterstützt.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Steuert, ob <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> während der Objektserialisierung und-Deserialisierung eine größere Array Größe verwendet. Legen Sie diesen Schalter auf `true` fest, um die Leistung der Serialisierung und Deserialisierung großer Objekt Diagramme nach Typen wie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>zu verbessern. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Steuert, ob der <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType>-Konstruktor die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType>-Eigenschaft des neuen Objekts mit einem vorhandenen Objekt Verweis festlegt. Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Steuert, ob der Versuch, eine <xref:System.Security.Cryptography.AesCryptoServiceProvider> Entschlüsselungs wiederzuverwenden, eine <xref:System.Security.Cryptography.CryptographicException>auslöst. Weitere Informationen finden Sie unter [AesCryptoServiceProvider Entschlüsselungs stellt eine wiederverwendbare Transformation bereit](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Steuert, ob der Wert der [CspParameters. Parameter WindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) -Eigenschaft ein [IntPtr](xref:System.IntPtr) ist, das die Speicherposition eines Fenster Handles darstellt, oder ob es sich um ein Fenster Handle (HWND) handelt. Weitere Informationen finden Sie unter [Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Steuert, ob durch die Verwendung verwalteter Kryptografieklassen im-PPS-Modus eine <xref:System.Security.Cryptography.CryptographicException> (`true`) ausgelöst oder die Implementierung von Systembibliotheken (`false`) verwendet wird.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedCms-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Steuert, ob die <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType>-Methode alle benannten Kurven, die vom Betriebssystem unterstützt werden (`false`), ordnungsgemäß verarbeitet oder auf das Legacy Verhalten zurückgesetzt wird.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige SignedXml-Vorgänge SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Bestimmt, ob der `TransportWithMessageCredential` Sicherheitsmodus Nachrichten mit einem unsignierten "to"-Header zulässt. Dies ist ein Opt-in-Switch. Weitere Informationen finden Sie unter [Lauf Zeit Änderungen in der .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Steuert, ob der <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>-Konstruktor eine <xref:System.ArgumentException> auslöst, wenn eines der Elemente `null`ist.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Bestimmt, ob der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicher Anbieter zu verwenden, eine Ausnahme auslöst. Weitere Informationen finden [Sie unter WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe von CNG gespeichert](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)wurden.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Wenn Sie den HTTP-Transport mit einem selbstgeh osteten Dienst verwenden, wird von WCF beim Festlegen dieses Werts auf `true` eine Anwendung ignoriert, die die `Connection: close`-Kopfzeile den Antwort Headern für eine Anforderung hinzufügt. Wenn dieser Wert auf `false` festgelegt wird, kann der `Connection: close`-Header den Antwort Headern hinzugefügt werden, was dazu führt, dass der Anforderungs Socket geschlossen wird, nachdem eine Antwort gesendet wurde.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Behandelt Deadlocks, die sich aus der Einschränkung von Instanzen eines Wiedereintritts enden dienstanzen auf einen einzelnen Ausführungs Thread ergeben.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Zusammen mit `Switch.System.Net.DontEnableSchUseStrongCrypto`bestimmt, ob die WCF-Nachrichten Sicherheit TLS 1,1 und TLS 1,2 verwendet.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Der Wert `false` legt die Standardkonfiguration fest, um dem Betriebssystem das Auswählen des Protokolls zu ermöglichen. Der Wert `true` legt den Standardwert auf das höchste verfügbare Protokoll fest. (Auch für den Wartungs Zweig früherer Frameworkversionen verfügbar)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Bestimmt, ob der standardmäßige Nachrichten Signatur Algorithmus für MSMQ-Nachrichten in WCF SHA1 oder SHA256 ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Steuert, ob WCF einen SHA1-oder einen SHA256-Hash verwendet, um zufällige Namen für Named Pipes zu generieren.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Steuert, ob eine [NullReferenceException](xref:System.NullReferenceException) ausgelöst werden soll, wenn die Ausnahme Meldung NULL ist.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Steuert, ob für den Dienst Start ausgelöste Ausnahmen an den Aufrufer der <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>-Methode weitergegeben werden.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Steuert, ob <xref:System.Threading.Timer> Instanzen die Leistungsverbesserungen für hochskalierbare Umgebungen nutzen. Wenn `true`, sind die Leistungsverbesserungen aktiviert. Wenn `false` (der Standardwert), werden diese deaktiviert.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Bestimmt, ob bestimmte Prozent codierte Zeichen, die manchmal decodiert waren, jetzt konsistent Links codiert sind. Wenn `true`, werden diese decodiert. Andernfalls `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Bestimmt die Handhabung von bidirektionalen Unicode-Zeichen in URIs. `true`, Sie aus URIs zu entfernen. `false`, um Sie beizubehalten und zu codieren.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Bestimmt, ob Windows Presentation Foundation einen alten Algorithmus (`true`) oder einen neuen Algorithmus (`false`) zum Zuordnen von Speicherplatz für \*Spalten anwendet. Weitere Informationen finden Sie unter [Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Steuert, ob ein Selector-Steuerelement oder ein Registerkarten-Steuerelement den Wert der ausgewählten Wert Eigenschaft immer aktualisiert, bevor das Auswahl Änderungs Ereignis erhöht wird.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Bestimmt, ob ein nicht-Adorner-basiertes Auswahl Rendering für die <xref:System.Windows.Controls.TextBox>-und <xref:System.Windows.Controls.PasswordBox>-Steuerelemente verfügbar ist, um den okdierten Text (`false`) zu verhindern, oder ob Text nur in der Adornerebene (`true`) gerendert wird.|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Steuert, ob benutzerdefinierte IList-Indexer falsch (`false`) oder ordnungsgemäß (`true`) von der <xref:System.Windows.Data.Binding?displayProperty=nameWithType>-Klasse verwendet werden.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Bestimmt, ob dpi-Änderungen auf einem pro-System-(Wert `false`) oder pro Monitor (Wert `true`) erfolgen.|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Steuert, ob Verbesserungen bei der Größenänderung von Steuerelementen in einer <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType>, wenn WPF im Überwachungsmodus pro Monitor ausgeführt wird, deaktiviert (`true`) oder aktiviert (`false`) ist.|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Bestimmt, ob der Entwickler die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> Aktion speziell verarbeiten muss, wenn der Steuerelement Text vorhanden ist. `true`, um die <xref:System.Windows.Forms.DomainUpDown.UpButton> Aktion zu verarbeiten. `false`, dass die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> Aktionen ordnungsgemäß synchronisiert werden.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Beendet den Code, der es einer benutzerdefinierten <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> Implementierung ermöglicht, Nachrichten sicher zu filtern, ohne eine Ausnahme auszulösen, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Bestimmt, ob die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft das Quell Steuerelement zurückgibt, wenn der Benutzer das Menü von einem <xref:System.Windows.Forms.ToolStripMenuItem> Steuerelement öffnet. Das Legacy Verhalten `true`, um `null`zurückzugeben. `false`, um die Quell Code Verwaltung zurückzugeben.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Steuert, ob die QuickInfo-Aufruf Unterstützung deaktiviert (`true`) oder aktiviert (`false`) ist. Das Aktivieren der Unterstützung von QuickInfo-aufrufen erfordert auch Legacy-Barrierefreiheits Funktionen, die durch `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`und `Switch.UseLegacyAccessibilityFeatures.3` deaktiviert (festgelegt auf `false`) definiert sind.|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Bestimmt, ob in WPF-Anwendungen ein optionaler, `WM_POINTER`basierter Fingereingabe-/tablettstiftstapel aktiviert ist. Weitere Informationen finden Sie [unter Entschärfung: Zeiger basierte Berührungs-und tablettstiftunterstützung](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md) .|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Bestimmt, ob der für Prüfsummen verwendete Standard Hash Algorithmus SHA256 (`false`) oder SHA1 (`true`) ist.<br>Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Steuert, ob eine Legacy- [NullReferenceException](xref:System.NullReferenceException) anstelle der Ausnahme ausgelöst wird, die die Ursache der Ausnahme genauer angibt (z. b. eine [directoriynotfoundexception](xref:System.IO.DirectoryNotFoundException) oder eine file [topics](xref:System.IO.FileNotFoundException)-Eigenschaft). Sie ist für die Verwendung durch Code vorgesehen, der von der Behandlung von [NullReferenceException](xref:System.NullReferenceException)abhängig ist. | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Steuert, ob beim Prüfsummen Hashwert von XOML-Dateien in Workflow Projektbuilds der MD5-Algorithmus (`true`) verwendet wird oder ob der SHA256-Algorithmus verwendet wird, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Steuert, ob ein Prüfsummen-Hash durch SqlTrackingService den MD5-Algorithmus (`true`) für zwischengespeicherte Zeichen folgen verwendet, oder ob er den SHA256-Algorithmus verwendet, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Steuert, ob ein Prüfsummen-Hashwert durch die Workflow Laufzeit den MD5-Algorithmus (`true`) für zwischengespeicherte Workflow Definitionen verwendet, oder ob er den SHA256-Algorithmus verwendet, der als Standard in .NET Framework 4,8 eingeführt wurde.<br>Microsoft empfiehlt SHA256 aufgrund der Konflikte mit MD5.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Steuert, ob Barrierefreiheits Funktionen, die mit .NET Framework 4.7.1 verfügbar sind, aktiviert oder deaktiviert sind. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Steuert, ob Barrierefreiheits Funktionen, die in .NET Framework 4.7.2 verfügbar sind, aktiviert (`false`) oder deaktiviert (`true`) sind. Wenn `true`, müssen `Switch.UseLegacyAccessibilityFeatures` auch `true` werden, um .NET Framework 4.7.1 Barrierefreiheits Funktionen zu aktivieren.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Steuert, ob in .NET Framework 4,8 eingeführte Barrierefreiheits Features aktiviert (`false`) oder deaktiviert (`true`) sind. Wenn `true`, müssen `Switch.UseLegacyAccessibilityFeatures` und `Switch.UseLegacyAccessibilityFeatures.2` ebenfalls `true`werden.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Steuert, ob Quick Infos angezeigt werden, wenn ein Benutzer mit dem Mauszeiger über ein WPF-Steuerelement (`true`) bewegt wird oder ob Sie sowohl auf dem Tastaturfokus als auch über die Tastenkombination (`false`, das Standardverhalten) angezeigt werden. Für Anwendungen, die auf .NET Framework 4,8 ausgeführt werden, aber auf frühere Versionen der .NET Framework abzielen, erfordert die Aktivierung von Tastaturfokus und Unterstützung von Tastenkombinationen, dass `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`und `Switch.UseLegacyAccessibilityFeatures.3` alle auf `false`festgelegt sind.|.NET Framework 4.8|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Steuert, ob leere schlüsselsequenzen in Verbund Schlüsseln durch die XSD-Schema Validierung ignoriert werden. Weitere Informationen finden Sie unter [Entschärfung: XML-Schema Validierung](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
> Anstatt einer Anwendungs Konfigurationsdatei ein `AppContextSwitchOverrides` Element hinzuzufügen, können Sie die Schalter auch Programm gesteuert festlegen, indem Sie die `static` ( C#in) oder `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.  
  
 Bibliotheks Entwickler können auch benutzerdefinierte Switches definieren, um Aufrufern zu ermöglichen, geänderte Funktionen zu abonnieren, die in späteren Versionen Ihrer Bibliotheken eingeführt wurden. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.AppContext>-Klasse.  
  
## <a name="switches-in-aspnet-applications"></a>Switches in ASP.NET-Anwendungen

Sie können eine ASP.NET-Anwendung so konfigurieren, dass Sie Kompatibilitäts Einstellungen verwendet, indem Sie dem [\<appSettings >](../appsettings/index.md) -Abschnitt der Datei "Web. config" ein [\<Add >](../appsettings/add-element-for-appsettings.md) -Element hinzufügen. 

Im folgenden Beispiel wird das `<add>`-Element verwendet, um dem Abschnitt `<appSettings>` einer Web. config-Datei zwei Einstellungen hinzuzufügen:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird das `AppContextSwitchOverrides`-Element verwendet, um einen einzelnen Anwendungskompatibilitäts-Switch, `Switch.System.Globalization.NoAsyncCurrentCulture`, zu definieren, der verhindert, dass die Kultur bei asynchronen Methoden aufrufen in Threads fließt.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 Im folgenden Beispiel werden die `AppContextSwitchOverrides`-Element verwendet, um zwei Anwendungskompatibilitäts-Switches `Switch.System.Globalization.NoAsyncCurrentCulture` und `Switch.System.IO.BlockLongPaths`zu definieren. Beachten Sie, dass die beiden Name/Wert-Paare durch ein Semikolon getrennt werden.  
  
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
- [\<Lauf Zeit > Element](runtime-element.md)
- [\<configuration> Element](../configuration-element.md)
