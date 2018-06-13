---
title: '&lt;AppContextSwitchOverrides&gt; Element'
ms.custom: updateeachrelease
ms.date: 04/19/2018
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d16ce7f2744869c812b9988e91edd153d9cb4fd2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747524"
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt; Element
Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.  
  
 \<configuration>  
 \<Common Language Runtime >  
\<AppContextSwitchOverrides>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut.<br /><br /> Definiert eine oder mehrere Switch-Namen und die zugehörigen booleschen Werte.|  
  
### <a name="value-attribute"></a>value-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|"Name = Value"|Der Name eines vordefinierten Switches zusammen mit seinen Wert (`true` oder `false`). Mehrere Schalter Name/Wert-Paare werden durch Semikolons getrennt (";"). Eine Liste der vordefinierten Schalternamen von .NET Framework unterstützt finden Sie unter dem Abschnitt "Hinweise".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit .NET Framework 4.6 der `<AppContextSwitchOverrides>` -Element in einer Konfigurationsdatei ermöglicht Aufrufern einer API zu bestimmen, ob ihre app Kompatibilität mit früheren Versionen einer Bibliothek beibehalten oder neue Funktionalität nutzen kann. Angenommen, wenn sich das Verhalten einer API zwischen zwei Versionen einer Bibliothek geändert hat die `<AppContextSwitchOverrides>` Element ermöglicht es dem Aufrufer von diesem-API, um das neue Verhalten bei Bibliotheksversionen abzuwählen, die die neue Funktionen zu unterstützen. Für apps, die in .NET Framework-APIs Aufrufen der `<AppContextSwitchOverrides>` Element erlaubt, deren apps auf eine frühere Version von .NET Framework in die neue Funktionalität deaktiviert wird, wenn ihre app auf eine Version von .NET Framework ausgeführt wird, die mit, Aufrufern die Funktionalität.  
  
 Die `value` Attribut von der `<AppContextSwitchOverrides>` Element besteht aus einer einzelnen Zeichenfolge, aus denen ein oder mehrere durch Semikolons getrennte Name/Wert-Paare besteht.  Jeder Name identifiziert eine Kompatibilitätsschalter und der entsprechende Wert ist ein boolescher Wert (`true` oder `false`), der angibt, ob der Schalter festgelegt ist. Standardmäßig ist der Switch `false`, und Bibliotheken bieten die neue Funktionen. Sie nur die vorherige Funktionalität bieten, wenn der Schalter festgelegt ist (d. h. der Wert ist `true`). Dadurch wird ein neues Verhalten für eine vorhandene API bereitstellen, während gleichzeitig der Aufrufer auf das vorherige Verhalten der neuen Funktionalität Betaphase angewiesenen Mitarbeitern Bibliotheken.  
  
 .NET Framework unterstützt die folgenden Optionen:  
  
|SwitchName|Beschreibung|Eingeführt|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Steuert, ob Windows Presentation Foundation Vorgängerversion ein Algorithmus für das Steuerelementlayout verwendet. Weitere Informationen finden Sie unter [Entschärfung: WPF-Layout](~/docs/framework/migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Steuert, ob der für die Signierung Teile eines Pakets durch PackageDigitalSignatureManager verwendete Standardalgorithmus SHA1 oder SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Bei Festlegung auf `false`, ermöglicht das Debuggen von XAML-basierten Workflow-Projekte mit Visual Studio, wenn FIPS aktiviert ist. Ohne diese einem <xref:System.NullReferenceException> im Aufrufe von Methoden in der Assembly System.Activities ausgelöst wird.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Steuert, ob die Prüfsumme für eine Workflowinstanz im Debugger MD5 oder SHA1 verwendet. | .NET Framework 4.7|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Steuert, ob auftretenden Fehlern stapelverfolgungen erhalten, bei Verwendung von portablen PDBs Quellinformationen und die Zeilennummer enthalten können. `false` Quelle und die Zeilennummer Informationen eingeschlossen; andernfalls `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Steuerelemente, ob die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> Methode löst eine Ausnahme aus, wenn ein <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist. Weitere Informationen finden Sie unter [Entschärfung: PNG-Bilder in Symbolobjekten](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|  
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Bestimmt, ob <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> Objekte sind ordnungsgemäß freigegeben, wenn die Auflistung von hinzugefügt die <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> Methode. `true` um die Legacyverhalten zu verwalten. `false` alle privaten Schriftartenobjekte freizugeben. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|Steuert, ob die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> für Netzwerkdrucker optimiert ist. Weitere Informationen finden Sie unter [Übersicht über das PrintPreviewDialog-Steuerelement](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Steuert, ob asynchrone Vorgänge nicht aus dem Kontext des aufrufenden Threads übergeben. Weitere Informationen finden Sie unter [CurrentCulture und CurrentUICulture fließen, mehrere Vorgänge](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Steuert, ob die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> Methode versucht, den Anspruchstyp nur mit den letzten DNS-Eintrag übereinstimmen. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet.FindClaims-Methode](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Steuert, ob AuthorizationContext.Empty ein änderbares Objekt zurückgeben können.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Steuert, ob Pfade mit mehr als `MAX_PATH` (260 Zeichen) Auslösen einer <xref:System.IO.PathTooLongException>. Weitere Informationen finden Sie unter [Unterstützung für lange Pfad](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Steuert, ob native OS-Routinen für die dekomprimierung von dienen der <xref:System.IO.Compression.DeflateStream> Klasse. `false` auf systemeigene APIs verwenden. `true` verwenden die <xref:System.IO.Compression.DeflateStream> Implementierung.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Verwendet den umgekehrten Schrägstrich ("\\") anstelle der Schrägstrich ("/") als Pfadtrennzeichen für den in der <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> Eigenschaft. Weitere Informationen finden Sie unter [Entschärfung: ZipArchiveEntry.FullName Pfadtrennzeichen](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Steuert, ob Systemausnahmen ausgeführt, die in Hintergrundthreads mit erstellt ausgelöst werden <xref:System.IO.Ports.SerialPort> Streams beenden den Prozess.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Steuert, ob die legacy-Pfad-Normalisierung verwendet, und die URI-Pfade werden unterstützt, indem Sie die <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> Methoden. Weitere Informationen finden Sie unter [Entschärfung: Pfad Normalisierung](~/docs/framework/migration-guide/mitigation-path-normalization.md) und [Entschärfung: Pfad Doppelpunkt überprüft](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Steuert, ob ein Test auf Gleichheit vergleicht die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> -Eigenschaft des zweiten Objekts. Weitere Informationen finden Sie unter [falschen Implementierung von MemberDescriptor.Equals](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deaktiviert die zertifikatüberprüfung erweiterte Schlüsselverwendung (EKU)-Objekt-ID (OID). Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deaktiviert die Minderung TLS1. 0 Browser ausnutzen für SSL/TLS (BEAST) durch die Verwendung des SCH_SEND_AUX_RECORD deaktivieren.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Steuert, ob die <xref:System.Net.ServicePointManager?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType> Klassen können das SSL 3.0-Protokoll verwenden. Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](~/docs/framework/migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Zurücksetzen auf den Standardwert Tls12, Tls11, Tls SystemDefault TLS-Versionen wird deaktiviert.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deaktiviert die serverseitige Benachrichtigungen SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Steuert, ob die [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) einige Steuerzeichen, die auf der Grundlage der Standards ECMAScript V6 und V8 serialisiert. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Steuert, ob die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützt mehrere Korrekturen oder nur eine einzelne Anpassung für eine Zeitzone. Wenn `true`, verwendet der <xref:System.TimeZoneInfo> Geben Sie zum Serialisieren und Deserialisieren von Datums-und Uhrzeitdaten; andernfalls wird die <xref:System.TimeZone> -Typ, der mehrere Anpassungsregeln nicht unterstützt.|.NET Framework 4.6.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Steuert, ob die <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> Konstruktor legt des neuen Objekts <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> Eigenschaft mit einem vorhandenen Objektverweis. Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Steuert, ob der Versuch, wiederverwenden ein <xref:System.Security.Cryptography.AesCryptoServiceProvider> Entschlüsselungsmethode löst eine <xref:System.Security.Cryptography.CryptographicException>. Weitere Informationen finden Sie unter [AesCryptoServiceProvider Entschlüsselungsmethode bietet eine wieder verwendbare Transformation](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Steuerelemente, ob der Wert von der [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) Eigenschaft ist ein [IntPtr](xref:System.IntPtr) , stellt die Speicheradresse eines Fensters behandeln, oder ob es ein Fensterhandle (HWND) ist. Weitere Informationen finden Sie unter [Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige Vorgänge SignedCMS SHA1 oder SHA256. |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Bestimmt, ob der Standardwert für einige Vorgänge SignedXML SHA1 oder SHA256. |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Bestimmt, ob die `TransportWithMessageCredential` Sicherheitsmodus kann Nachrichten einen nicht signierten "to"-Header. Dies ist ein Opt-in-Schalter. Weitere Informationen finden Sie unter [Laufzeitänderungen in .NET Framework 4.6.1](https://msdn.microsoft.com/library/mt592686.aspx#WCF).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Steuert, ob die <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> löst der Konstruktor ein <xref:System.ArgumentException> Wenn eines der Elemente ist `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Bestimmt, ob der Versuch, verwenden Sie X509 mit Zertifikaten ein CSG softwareschlüsselspeicher-Anbieter eine Ausnahme auslöst. Weitere Informationen finden Sie unter [Sicherheit für WCF-Transport unterstützt Zertifikate mit CNG gespeichert](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Wenn Sie den HTTP-Transport mit einem selbst gehosteten Dienst zu verwenden, wenn dieser Wert auf `true` bewirkt, dass WCF ignorieren einer Anwendung hinzufügen der `Connection: close` Header in die Antwortheader für eine Anforderung. Wenn dieser Wert auf `false` kann durch das Hinzufügen der `Connection: close` Header in die Antwortheader, dies führt die Anforderung Socket schließen, nachdem eine Antwort gesendet wurde.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Handles-Deadlocks, die aus Instanzen eines Diensts wiedereintrittsfähig auf einen einzelnen Thread der Ausführung zu einem Zeitpunkt einschränken.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Zusammen mit `Switch.System.Net.DontEnableSchUseStrongCrypto`, bestimmt, ob WCF-nachrichtensicherheit TLS 1.1 und TLS 1.2 verwendet.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Der Wert `false` legt die Standardkonfiguration, um das Betriebssystem auswählen des Protokolls zu ermöglichen. Der Wert `true` legt den Standardwert des höchsten Protokolls verfügbar. (Auch auf servicing Branch von früheren Framework-Versionen verfügbar)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Bestimmt, ob die Standardnachricht Signaturalgorithmus für MSMQ-Nachrichten in WCF SHA1 oder SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Steuert, ob WCF ein SHA1- oder eine SHA256-Hash verwendet, um zufällige Namen für named Pipes zu generieren.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Steuert, ob das Auslösen einer [NullReferenceException](xref:System.NullReferenceException) Wenn die Ausnahmemeldung null ist.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Steuert, ob beim Start des Diensts ausgelöste Ausnahmen an den Aufrufer des weitergegeben werden die <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> Methode.|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Bestimmt, ob bestimmte Zeichen mit Prozentzeichen codiert, die manchmal decodiert wurden jetzt konsistente linken codiert sind. Wenn `true`, werden decodierte ist, andernfalls `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Bestimmt die Behandlung von bidirektionalen Unicodezeichen in URIs an. `true` Diese URIs entfernt; `false` zu erhalten und Prozent-transportierenden.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Bestimmt, ob Windows Presentation Foundation einen alte-Algorithmus wendet (`true`) oder einen neuen Algorithmus (`false`) beim Reservieren von Speicherplatz für \*-Spalten. Weitere Informationen finden Sie unter [Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Steuert, ob ein Selektor oder Tabstopp steuern immer den Wert der seine ausgewählte Value-Eigenschaft, die vor dem Auslösen der Auswahl aktualisiert das geänderte Ereignis.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Bestimmt, ob nicht Adorner basierend Auswahl Rendering für steht die <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.PasswordBox> Steuerelemente zu verhindern, dass Text okkludierte (`false`), oder gibt an, ob der Text nur in der Adornerebene gerendert wird (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Bestimmt, ob die DPI-Änderungen in einem pro-System (Wert `false`) oder pro-Monitor (Wert `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Bestimmt, ob der Entwickler speziell behandeln muss die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> Aktion beim Steuerelementtext vorhanden ist. `true` Behandeln der <xref:System.Windows.Forms.DomainUpDown.UpButton> Aktion; `false` für die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> Aktionen ordnungsgemäß synchronisiert sind.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|"OPTS" aus dem Code, der eine benutzerdefinierte ermöglicht <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> -Implementierung, die Nachrichten sicher filtern, ohne eine Ausnahme auszulösen bei der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> -Methode aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Bestimmt, ob die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> Eigenschaft gibt die Datenquellen-Steuerelement zurück, wenn der Benutzer im Menü aus einer geschachtelten öffnet <xref:System.Windows.Forms.ToolStripMenuItem> Steuerelement. `true` zurückzugebenden `null`, Legacyverhalten; `false` auf die Datenquellen-Steuerelements zurück.|.NET Framework 4.7.2|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Bestimmt, ob ein optionales `WM_POINTER`-Basis Touch/Tablettstift-Stapel in WPF-Anwendungen aktiviert ist. Weitere Informationen finden Sie unter [Entschärfung: zeigerbasierten Touch- und Tablettstift-Unterstützung](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Bestimmt, ob der Standardhashalgorithmus, der für die Prüfsummen verwendet SHA256 ist (`false`) oder SHA1 (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Steuert, ob eine Vorgängerversion [NullReferenceException](xref:System.NullReferenceException) wird ausgelöst, anstatt die Ausnahme, die die Ursache der Ausnahme genauer gesagt gibt an (z. B. eine [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) oder eine [ FileNotFoundException](xref:System.IO.FileNotFoundException). Es dient zur Verwendung von Code, von denen abhängt Behandlung der [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|Steuert werden, ob die Eingabehilfen verfügbar beginnend mit .NET Framework 4.7.1 aktiviert oder deaktiviert. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Steuert, ob in .NET Framework 4.7.2 verfügbaren Eingabehilfen sind aktiviert (`false`) oder deaktiviert (`true`). Wenn `true`, `Switch.UseLegacyAccessibilityFeatures` zudem muss `true` So aktivieren Sie .NET Framework 4.7.1 Eingabehilfen.|.NET Framework 4.7.2|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Steuert, ob leere schlüsselsequenzen in zusammengesetzten Schlüsseln von XSD-schemavalidierung ignoriert werden. Weitere Informationen finden Sie unter [Minderung: XML-Schema-Validation](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
>  Anstatt ein `AppContextSwitchOverrides` Element einer Anwendungskonfigurationsdatei, Sie können auch programmgesteuert festlegen, die Schalter durch Aufrufen der `static` (in c#) oder `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> Methode.  
  
 Entwickler von Bibliotheken können auch benutzerdefinierte Schalter verwenden, um Aufrufern das geänderte Funktionen in höheren Versionen ihrer Bibliotheken eingeführt abzuwählen ermöglichen definieren. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.AppContext>-Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AppContextSwitchOverrides` -Elements definieren Sie eine einzelne Anwendung-Kompatibilitätsschalter `Switch.System.Globalization.NoAsyncCurrentCulture`, Kultur, die verhindert, dass threadübergreifend in asynchrone Methodenaufrufe fließen.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 Im folgenden Beispiel wird die `AppContextSwitchOverrides` -Elements definieren Sie zwei Anwendung Kompatibilitätsschalter `Switch.System.Globalization.NoAsyncCurrentCulture` und `Switch.System.IO.BlockLongPaths`. Beachten Sie, dass ein Semikolon der beiden Name/Wert-Paare trennt.  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AppContext?displayProperty=nameWithType>  
 [\<Common Language Runtime >-Element](runtime-element.md)  
 [\<configuration> Element](../configuration-element.md)
