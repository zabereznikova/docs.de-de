---
title: '&lt;AppContextSwitchOverrides&gt; Element'
ms.custom: 
ms.date: 10/17/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ed1b11cef909af153e43d61e71a4875648bdbfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt; Element
Definiert mindestens eine Option, die von der <xref:System.AppContext>-Klasse für die Bereitstellung eines Mechanismus zum Deaktivieren neuer Funktionen verwendet wird.  
  
 \<configuration>  
 \<Common Language Runtime >  
\<AppContextSwitchOverrides >  
  
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
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Bei Festlegung auf `false`, ermöglicht das Debuggen von XAML-basierten Workflow-Projekte mit Visual Studio, wenn FIPS aktiviert ist. Ohne diese einem <xref:System.NullReferenceException> im Aufrufe von Methoden in der Assembly System.Activities ausgelöst wird.|.NET Framework 4.7|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Steuerelemente, ob die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> Methode löst eine Ausnahme aus, wenn ein <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist. Weitere Informationen finden Sie unter [Entschärfung: PNG-Bilder in Symbolobjekten](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|  
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Steuert, ob asynchrone Vorgänge nicht aus dem Kontext des aufrufenden Threads übergeben. Weitere Informationen finden Sie unter [CurrentCulture und CurrentUICulture fließen, mehrere Vorgänge](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Steuert, ob die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> Methode versucht, den Anspruchstyp nur mit den letzten DNS-Eintrag übereinstimmen. Weitere Informationen finden Sie unter [Entschärfung: X509CertificateClaimSet.FindClaims-Methode](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.BlockLongPaths`|Steuert, ob Pfade mit mehr als `MAX_PATH` (260 Zeichen) Auslösen einer <xref:System.IO.PathTooLongException>. Weitere Informationen finden Sie unter [Unterstützung für lange Pfad](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Verwendet den umgekehrten Schrägstrich ("\\") anstelle der Schrägstrich ("/") als Pfadtrennzeichen für den in der <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> Eigenschaft. Weitere Informationen finden Sie unter [Entschärfung: ZipArchiveEntry.FullName Pfadtrennzeichen](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Steuert, ob die legacy-Pfad-Normalisierung verwendet, und die URI-Pfade werden unterstützt, indem Sie die <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> Methoden. Weitere Informationen finden Sie unter [Entschärfung: Pfad Normalisierung](~/docs/framework/migration-guide/mitigation-path-normalization.md) und [Entschärfung: Pfad Doppelpunkt überprüft](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Steuert, ob ein Test auf Gleichheit vergleicht die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> -Eigenschaft des zweiten Objekts. Weitere Informationen finden Sie unter [falschen Implementierung von MemberDescriptor.Equals](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deaktiviert die zertifikatüberprüfung erweiterte Schlüsselverwendung (EKU)-Objekt-ID (OID). Eine erweiterte Schlüsselverwendung (EKU)-Erweiterung ist eine Auflistung von Objektbezeichnern (OIDs), die angeben, die Anwendungen, die den Schlüssel zu verwenden.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deaktiviert die Minderung TLS1. 0 Browser ausnutzen für SSL/TLS (BEAST) durch die Verwendung des SCH_SEND_AUX_RECORD deaktivieren.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Steuert, ob die <xref:System.Net.ServicePointManager?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType> Klassen können das SSL 3.0-Protokoll verwenden. Weitere Informationen finden Sie unter [Entschärfung: TLS-Protokolle](~/docs/framework/migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Zurücksetzen auf den Standardwert Tls12, Tls11, Tls SystemDefault TLS-Versionen wird deaktiviert.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deaktiviert die serverseitige Benachrichtigungen SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Steuert, ob die [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) einige Steuerzeichen, die auf der Grundlage der Standards ECMAScript V6 und V8 serialisiert. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)| .NET Framework 4.7 |
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Steuert, ob die <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> Konstruktor legt des neuen Objekts <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> Eigenschaft mit einem vorhandenen Objektverweis. Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Steuert, ob der Versuch, wiederverwenden ein <xref:System.Security.Cryptography.AesCryptoServiceProvider> Entschlüsselungsmethode löst eine <xref:System.Security.Cryptography.CryptographicException>. Weitere Informationen finden Sie unter AesCryptoServiceProvider Entschlüsselungsmethode eine wieder verwendbare transform](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform) bietet.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Steuerelemente, ob der Wert von der [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) Eigenschaft ist ein [IntPtr](xref:System.IntPtr) , stellt die Speicheradresse eines Fensters behandeln, oder ob es ein Fensterhandle (HWND) ist. Weitere Informationen finden Sie unter [Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md). |.NET Framework 4.7|   
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Bestimmt, ob die `TransportWithMessageCredential` Sicherheitsmodus kann Nachrichten einen nicht signierten "to"-Header. Dies ist ein Opt-in-Schalter. Weitere Informationen finden Sie unter [Laufzeitänderungen in .NET Framework 4.6.1](https://msdn.microsoft.com/library/mt592686.aspx#WCF).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Bestimmt, ob der Versuch, verwenden Sie X509 mit Zertifikaten ein CSG softwareschlüsselspeicher-Anbieter eine Ausnahme auslöst. Weitere Informationen finden Sie unter [Sicherheit für WCF-Transport unterstützt Zertifikate mit CNG gespeichert](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Zusammen mit `Switch.System.Net.DontEnableSchUseStrongCrypto`, bestimmt, ob WCF-nachrichtensicherheit TLS 1.1 und TLS 1.2 verwendet.|.NET Framework 4.7 |    
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Bestimmt, ob Windows Presentation Foundation einen alte-Algorithmus wendet (`true`) oder einen neuen Algorithmus (`false`) beim Reservieren von Speicherplatz für \*-Spalten. Weitere Informationen finden Sie unter [Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md). |.NET Framework 4.7 |
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|"OPTS" aus dem Code, der eine benutzerdefinierte ermöglicht <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> -Implementierung, die Nachrichten sicher filtern, ohne eine Ausnahme auszulösen bei der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> -Methode aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Bestimmt, ob ein optionales `WM_POINTER`-Basis Touch/Tablettstift-Stapel in WPF-Anwendungen aktiviert ist. Weitere Informationen finden Sie unter [Entschärfung: zeigerbasierten Touch- und Tablettstift-Unterstützung](Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md) | 
|`Switch.System.Windows.Media.ImageSourceConverter`<br/>`OverrideExceptionWithNullReferenceException`|Steuert, ob eine Vorgängerversion [NullReferenceException](xref:System.NullReferenceException) wird ausgelöst, anstatt die Ausnahme, die die Ursache der Ausnahme genauer gesagt gibt an (z. B. eine [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) oder eine [ FileNotFoundException](xref:System.IO.FileNotFoundException). Es dient zur Verwendung von Code, von denen abhängt Behandlung der [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
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
 [AppContext](xref:System.AppContext?qualifyHint=False&autoUpgrade=True)  
 [\<Common Language Runtime >-Element](runtime-element.md)  
 [\<configuration>-Element](../configuration-element.md)
