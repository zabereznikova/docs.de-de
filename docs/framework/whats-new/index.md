---
title: "Neuigkeiten in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Neuigkeiten [.NET Framework]"
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 287
---
# Neuigkeiten in .NET Framework
<a name="introduction"></a>Dieser Artikel beschreibt wichtige neue Features und Verbesserungen in den folgenden Versionen von .NET Framework:  
  
 [.NET Framework 4.6.2](#v462)   
 [.NET Framework 4.6.1](#v461)   
 [.NET 2015 und .NET Framework 4.6](#v46)   
 [.NET Framework 4.5.2](#v452)   
 [.NET Framework 4.5.1](#v451)   
 [.NET Framework 4.5](#core)  
  
 Dieser Artikel enthält keine umfassenden Informationen zu jeder neuen Funktion und unterliegt möglichen Änderungen. Allgemeine Informationen zu .NET Framework finden Sie unter [Getting Started](../../../docs/framework/get-started/index.md). Informationen zu unterstützten Plattformen finden Sie unter [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md). Downloadlinks und installationsanweisungen finden Sie unter [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md).  
  
> [!NOTE]
>  .NET Framework-Team veröffentlicht Features Out of Band mit NuGet, um die plattformunterstützung zu erweitern und neuen Funktionen, z. B. unveränderliche Auflistungen und SIMD-fähigen vektortypen einzuführen. Weitere Informationen finden Sie unter [zusätzliche Klassenbibliotheken und APIs](../../../ml/index.xml) und [der .NET Framework und Out-of-Band-Versionen](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). Finden Sie unter einem [vollständige Liste von NuGet-Paketen](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) für .NET Framework oder abonnieren Sie [unseres Feeds](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).  
  
<a name="v462"></a>   
## <a name="introducing-the-net-framework-462"></a>Einführung in .NET Framework 4.6.2  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] baut auf .NET Framework 4.6 und 4.6.1 auf und umfasst zahlreiche Fehlerkorrekturen und neue Funktionen in einem gewohnt stabilen Produkt.  
  
### <a name="downloading-and-installing-the-net-framework-462"></a>Herunterladen und Installieren von .NET Framework 4.6.2  
 Sie können [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] von den folgenden Speicherorten herunterladen:  
  
-   [.NET Framework 4.6.2 Webinstaller](http://go.microsoft.com/fwlink/?LinkId=780597)  
  
-   [NET Framework 4.6.2 Offline-Installer](http://go.microsoft.com/fwlink/?LinkId=780601)  
  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] kann unter Windows 10, Windows 8.1, Windows 7 und den entsprechenden Serverplattformen, beginnend mit Windows Server 2008 R2 SP1, installiert werden. Sie können [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wahlweise mit dem Webinstaller oder Offlineinstaller installieren. Die empfohlene Vorgehensweise für die meisten Benutzer ist die Verwendung des Webinstallers.  
  
 Sie können als Ziel der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] in Visual Studio 2012 oder höher installieren der [.NET Framework 4.6.2 Developer Pack](http://go.microsoft.com/fwlink/?LinkId=780617).  
  
### <a name="whats-new-in-the-net-framework-462"></a>Neuigkeiten in .NET Framework 4.6.2  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] enthält neue Features in den folgenden Bereichen:  
  
-   [ASP.NET](#ASPNET462)  
  
-   [Zeichenkategorien](#Strings)  
  
-   [Kryptografie](#Crypto462)  
  
-   [SqlClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Konvertieren von Windows Forms und WPF-apps in UWP-apps](#UWPConvert)  
  
-   [Verbesserungen beim Debugging](#Debug462)  
  
 Für eine Liste der neuen APIs erweitert die [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], finden Sie unter [.NET Framework 4.6.2 API-Änderungen](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) auf GitHub. Eine Liste der Features Verbesserungen und Fehlerbehebungen in den [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], finden Sie unter [.NET Framework 4.6.2 API-Änderungen](http://go.microsoft.com/fwlink/?LinkId=708778) auf GitHub.  Weitere Informationen finden Sie unter [Ankündigung von .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) im .NET-Blog.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] umfasst ASP.NET die folgenden Verbesserungen:  
  
 **Verbesserte Unterstützung für lokalisierte Fehlermeldungen im Daten-Anmerkung Validierungssteuerelemente**  
 Mit Validierungssteuerelementen für Datenanmerkungen können Sie eine Überprüfung durchführen, indem Sie mindestens ein Attribut einer Klasseneigenschaft hinzufügen. Des Attributs <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> Element definiert den Text der Fehlermeldung aus, wenn die Validierung fehlschlägt. Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ist es einfach, mit ASP.NET Fehlermeldungen zu lokalisieren. Fehlermeldungen werden lokalisiert, wenn:  
  
1.  Die <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> in das Validierungsattribut bereitgestellt wird.  
  
2.  die Ressourcendatei im Ordner „App_LocalResources“ gespeichert ist.  
  
3.  Der Name der lokalisierten Ressourcendatei hat die Form `DataAnnotation.Localization.{` *Namen*`}.resx`, wobei *Namen* Namen einer Kultur im Format *LanguageCode*`-`*Landes-/Regionskennzahl* oder *LanguageCode*.  
  
4.  Der Schlüssel der Ressource ist der zugewiesene Zeichenfolge die <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> -Attribut, und der Wert ist die lokalisierte Fehlermeldung.  
  
 Das folgende anmerkungsattribut definiert z. B. die Standardkultur Fehlermeldung für eine ungültige Bewertung.  
  
```csharp  
  
public class RatingInfo  
{  
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]  
   [Display(Name = "Your Rating")]  
   public int Rating { get; set; }  
}  
  
```  
  
```vb  
  
Public Class RatingInfo  
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>  
   <Display(Name = "Your Rating")>  
   Public Property Rating As Integer = 1  
End Class  
  
```  
  
 Dann können Sie eine Ressourcendatei DataAnnotation.Localization.fr.resx, erstellen, deren Schlüssel die Zeichenfolge der Fehlermeldung ist und dessen Wert ist die lokalisierte Fehlermeldung. Die Datei muss vorhanden sein, der `App.LocalResources` Ordner. Beispielsweise ist im folgenden die Schlüssel und seinen Wert in eine lokalisierte Fehlermeldung für Französisch (fr) Sprache:  
  
|Name|Wert|  
|----------|-----------|  
|Die Bewertung muss zwischen 1 und 10 liegen.|LA Hinweis "doit" Être umfassen Entre 1 und 10.|  
  
 Diese Datei kann dann  
  
 Darüber hinaus ist die Lokalisierung der Datenanmerkung erweiterbar. Entwickler können eigene Zeichenfolge Lokalisierungsexperten Anbieter schließen Sie durch die Implementierung der <xref:System.Web.Globalization.IStringLocalizerProvider> Schnittstelle, um an einer beliebigen Stelle in der Lokalisierungszeichenfolge nicht in einer Ressourcendatei speichern.  
  
 **Async-Unterstützung mit Sitzungszustandsspeicher-Anbieter**  
 ASP.NET erlaubt nun, dass Methoden, die eine Aufgabe zurückgeben, zusammen mit dem Anbieter für die Speicherung von Daten aus der Variable „Sitzungszustand“ verwendet werden können. Dadurch stehen ASP .NET-Apps die Vorteile zur Verfügung, die async in Sachen Skalierbarkeit bietet. Unterstützt asynchrone Vorgänge mit dem Sitzungsstatus Zertifikatsspeicher Anbieter, ASP.NET beinhaltet eine neue Schnittstelle, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=fullName>, erbt von <xref:System.Web.IHttpModule> und ermöglicht es Entwicklern, ihre eigenen Sitzungsstatus Modul "und" Async Sitzungszustandsspeicher Anbieter implementieren. Die Schnittstelle wird wie folgt definiert:  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 Darüber hinaus die <xref:System.Web.SessionState.SessionStateUtility> Klasse enthält zwei neue Methoden <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> und <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, die verwendet werden kann, um asynchrone Vorgänge zu unterstützen.  
  
 **Async-Unterstützung für Ausgabecacheanbieter**  
 Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], können Methoden, die Aufgaben zurückgeben, mit Ausgabecacheanbietern verwendet werden, um die Vorteile der Skalierbarkeit von Async bereitzustellen.  Anbieter, die diese Methoden bereitstellen, verringern die Anzahl blockierter Threads auf einem Webserver und verbessern die Skalierbarkeit eines ASP.NET-Diensts.  
  
 Die folgenden APIs wurden hinzugefügt, um asynchrone Ausgabecacheanbieter zu unterstützen:  
  
-   Die <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=fullName> -Klasse, die von erbt <xref:System.Web.Caching.OutputCacheProvider?displayProperty=fullName> und ermöglicht Entwicklern die Implementierung einer asynchronen Ausgabecacheanbieter.  
  
-   Die <xref:System.Web.Caching.OutputCacheUtility> -Klasse, die Hilfsmethoden zum Konfigurieren des Ausgabecaches bereitstellt.  
  
-   18 neue Methoden in der <xref:System.Web.HttpCachePolicy?displayProperty=fullName>Klasse. Dazu gehören <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, und <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.  
  
-   2 neue Methoden in der <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=fullName> Klasse: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> und <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.  
  
-   2 neue Methoden in der <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=fullName> Klasse: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> und <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.  
  
-   2 neue Methoden in der <xref:System.Web.HttpCacheVaryByParams?displayProperty=fullName> Klasse: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> und <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.  
  
-   In der <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=fullName> -Klasse, die <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> Methode.  
  
-   In der <xref:System.Web.Caching.CacheDependency>, <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> Methode.  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>Zeichenkategorien  
 Zeichen in der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] klassifiziert sind, basierend auf der [Unicode-Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], werden Zeichen basierend auf den Zeichenkategorien von Unicode 6.3 klassifiziert.  
  
 Unterstützung für Unicode-8.0 ist beschränkt auf die Klassifizierung von Zeichen von der <xref:System.Globalization.CharUnicodeInfo> Klasse und auf Typen und Methoden, die darauf basieren. Dazu gehören die <xref:System.Globalization.StringInfo> Klasse, die überladene <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName> -Methode, und die [Zeichenklassen](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) von der .NET Framework-Modul für reguläre Ausdrücke erkannt.  Der Vergleich und die Sortierung von Zeichen und Zeichenfolgen sind von dieser Änderung nicht betroffen und beruhen weiterhin auf dem zugrunde liegenden Betriebssystem oder auf Windows 7-Systemen auf Zeichendaten, die vom .NET Framework bereitgestellt wurden.  
  
 Änderungen in Zeichenkategorien Unicode 6.0 bis 7.0 Unicode-, finden Sie unter [im Unicode-Standard, Version 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) Unicode Consortium-Website. Änderungen von Unicode-7.0 auf Unicode-8.0, finden Sie unter [im Unicode-Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) Unicode Consortium-Website.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>Kryptografie  
 **Unterstützung für X509 Zertifikate mit FIPS 186-3-DSA**  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] unterstützt DSA X509-Zertifikate (Digital Signature Algorithm), deren Schlüssel die FIPS 186-2-1024-Bit-Grenze überschreiten.  
  
 Zusätzlich zur Unterstützung der größeren Schlüsselgrößen von FIPS 186-3, erlaubt [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] die Berechnung von Signaturen mit der SHA-2-Familie der Hashalgorithmen (SHA256, SHA384 und SHA512). FIPS 186-3 wird unterstützt durch den neuen <xref:System.Security.Cryptography.DSACng?displayProperty=fullName> Klasse.  
  
 Mit den neuesten Änderungen an der <xref:System.Security.Cryptography.RSA> -Klasse in .NET Framework 4.6 und die <xref:System.Security.Cryptography.ECDsa> -Klasse in .NET Framework 4.6.1, die <xref:System.Security.Cryptography.DSA> abstrakten Basisklasse in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] verfügt über zusätzliche Methoden zum Aufrufer Verwendung dieser Funktionen ohne Umwandlung. Rufen Sie die <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=fullName> Erweiterungsmethode zum Signieren von Daten, wie im folgenden Beispiel gezeigt.  
  
```csharp  
  
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPrivateKey())  
    {  
        return dsa.SignData(data, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```vb  
  
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()  
    Using DSA As DSA = cert.GetDSAPrivateKey()  
        Return DSA.SignData(data, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 Und rufen Sie die <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=fullName> Erweiterungsmethode zum Überprüfen von signierten Daten ab, wie im folgenden Beispiel gezeigt.  
  
```csharp  
  
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPublicKey())  
    {  
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```  
  
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean  
    Using dsa As DSA = cert.GetDSAPublicKey()  
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 **Erhöhte Übersichtlichkeit für Eingaben ECDiffieHellman schlüsselableitung Routinen**  
 In.NET Framework 3.5 wurde die Unterstützung der Elliptic Curve Diffie-Hellman-Schlüsselübereinstimmung mit drei verschiedenen Schlüsselableitungsfunktions-Routinen (KDF) hinzugefügt. Die Eingaben für die und die Routinen für sich selbst über Eigenschaften konfiguriert wurden, auf die <xref:System.Security.Cryptography.ECDiffieHellmanCng> Objekt. Da jedoch nicht jede Routine jede input-Eigenschaft liest,sorgte dies bisher bei Entwicklern für reichlich Verwirrungspotenzial.  
  
 In diesem in die [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], die folgenden drei Methoden hinzugefügt wurden die <xref:System.Security.Cryptography.ECDiffieHellman> Basisklasse, um diese Routinen KDF und ihre Eingaben klarer darstellen:  
  
|Die ECDiffieHellman-Methode|Beschreibung|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash (ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> Hash(secretPrepend || *x* || SecretAppend)<br /><br /> HASH (SecretPrepend OrElse *x* OrElse SecretAppend)<br /><br /> wobei *x* ist das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus.|  
|[DeriveKeyFromHmac (ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\], Byte\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HMAC (HmacKey SecretPrepend || *x* || SecretAppend)<br /><br /> HMAC (HmacKey SecretPrepend OrElse *x* OrElse SecretAppend)<br /><br /> wobei *x* ist das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus.|  
|[DeriveKeyTls (ECDiffieHellmanPublicKey, Byte\[\], Byte\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mit dem Ableitungsalgorithmus der TLS-Pseudozufallsfunktion (pseudo-random function; PRF) ab.|  
  
 **Unterstützung für die symmetrische Verschlüsselung beibehalten-Schlüssel**  
 Die Windows-Kryptografiebibliothek (Cryptography API: Next Generation; CNG) hat Unterstützung für die Speicherung persistenter symmetrischer Schlüssel und für die Verwendung von in der Hardware gespeicherter symmetrischer Schlüssel bereitgestellt. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ermöglicht Entwicklern, diese Funktion zu verwenden.  Da das Konzept des Schlüsselnamens und des Schlüsselanbieters implementierungsspezifisch ist, erfordert die Nutzung dieser Funktion die Verwendung des Konstruktors der konkreten Implementierungstypen anstatt der bevorzugten Herangehensweise des Unternehmens (z.B. durch aufrufen von `Aes.Create`).  
  
 Unterstützung für symmetrische Verschlüsselung beibehalten Schlüssel vorhanden ist, für die AES (<xref:System.Security.Cryptography.AesCng>) und 3DES (<xref:System.Security.Cryptography.TripleDESCng>) Algorithmen. Beispiel:  
  
```csharp  
  
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)  
{  
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))  
    {  
        aes.IV = iv;  
  
        // Using the zero-argument overload is required to make use of the persisted key  
        using (ICryptoTransform encryptor = aes.CreateEncryptor())  
        {  
            if (!encryptor.CanTransformMultipleBlocks)  
            {  
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");  
            }  
  
            return encryptor.TransformFinalBlock(data, 0, data.Length);  
        }  
    }  
}  
  
```  
  
```vb  
  
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()  
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)  
        Aes.IV = iv  
  
        ' Using the zero-argument overload Is required to make use of the persisted key  
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()  
            If Not encryptor.CanTransformMultipleBlocks Then  
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")  
            End If  
            Return encryptor.TransformFinalBlock(data, 0, data.Length)  
        End Using  
    End Using  
End Function  
  
```  
  
 **SignedXml-Unterstützung für das hashing von SHA-2**  
 Die [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] fügt Unterstützung für die <xref:System.Security.Cryptography.Xml.SignedXml> Klasse für RSA-SHA256, RSA-SHA384 und RSA-SHA512-PKCS&#1;-Signatur-Methoden und SHA256, SHA384 und SHA512 Verweis Digest-Algorithmen.  
  
 Die URI-Konstanten sind für offengelegt <xref:System.Security.Cryptography.Xml.SignedXml>:  
  
|SignedXml-Feld|Konstante|  
|---------------------|--------------|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 Alle Programme, die eine benutzerdefinierte registriert haben <xref:System.Security.Cryptography.SignatureDescription> Handler in <xref:System.Security.Cryptography.CryptoConfig> zum Hinzufügen der Unterstützung für diese Algorithmen weiterhin so ausgeführt, als würden Sie in der Vergangenheit, aber da gibt es jetzt Plattform Standardeinstellungen, die <xref:System.Security.Cryptography.CryptoConfig> Registrierung ist nicht mehr erforderlich.  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient?displayProperty=fullName>) enthält die folgenden neuen Funktionen in der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:  
  
 **Verbindungs-pooling und Timeouts mit Azure SQL-Datenbanken**  
 Wenn das Verbindungspooling aktiviert ist und ein Timeoutfehler oder ein anderer Anmeldefehler auftritt, wird eine Ausnahme zwischengespeichert sowie die zwischengespeicherte Ausnahme wird für jeden nachfolgenden Verbindungsversuch für die nächsten 5 Sekunden bis zu einer Minute.  Weitere Informationen finden Sie unter [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
 Dieses Verhalten ist bei einer Verbindung zu Azure SQL-Datenbanken unerwünscht, da Verbindungsversuche mit flüchtigen Fehlern fehlschlagen können, die normalerweise schnell wiederhergestellt werden. Das Sperrfristverhalten des Verbindungspools wird entfernt, wenn die Verbindungsversuche zu Azure SQL-Datenbanken fehlschlagen, damit erneute Verbindungsversuche leichter erfolgen können.  
  
 Mit dem Hinzufügen des neuen `PoolBlockingPeriod`-Schlüsselworts können Sie die Sperrfrist auswählen, die für Ihre App am besten geeignet ist. Mögliche Werte:  
  
 `Auto`  
 Die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einer Azure SQL-Datenbank herstellt, ist deaktiviert, und die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einem anderen SQL-Server herstellt, ist aktiviert. Dies ist der Standardwert. Wenn der Serverendpunktname eine der folgenden Endungen besitzt, werden sie als Azure SQL-Datenbanken bezeichnet:  
  
-   .database.windows.net  
  
-   .database.chinacloudapi.cn  
  
-   .database.usgovcloudapi.net  
  
-   .database.cloudapi.de  
  
 `AlwaysBlock`  
 Die Sperrfrist des Verbindungspools ist immer aktiviert.  
  
 `NeverBlock`  
 Die Sperrfrist des Verbindungspools ist immer deaktiviert.  
  
 **Verbesserungen für immer verschlüsselt.**  
 SQLClient führt zwei Verbesserungen für Always Encrypted ein:  
  
-   Verschlüsselungsmetadaten für Abfrageparameter werden nun zwischengespeichert, um die Leistung von parametrisierten Abfragen von verschlüsselten Datenbankspalten zu verbessert. Mit der <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=fullName> Eigenschaft festgelegt, um `true` (das ist der Standardwert), wenn dieselbe Abfrage mehrmals aufgerufen wird, der Client ruft Parametermetadaten vom Server nur einmal.  
  
-   Verschlüsselung wichtige Einträge im Schlüssel-Zwischenspeicher entfernt werden jetzt nach einer konfigurierbaren Zeitintervall festlegen, verwenden Sie die <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=fullName> Eigenschaft.  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Windows Communication Foundation in den folgenden Bereichen erweitert:  
  
 **Unterstützung für die Sicherheit von WCF-Transport für Zertifikate mit CNG gespeichert**  
 Die WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe der Windows-Kryptografiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn sich eine Anwendung auf den [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] bezieht, so ist diese Funktion standardmäßig aktiviert.  
  
 Für Anwendungen, die als Ziel der [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren jedoch ausgeführt werden, auf der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], dieses Feature kann aktiviert werden, indem Sie die folgende Zeile hinzu der [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) -Abschnitt der Datei app.config oder web.config.  
  
```xml  
  
<AppContextSwitchOverrides  
    value="Switch.System.ServiceModel.DisableCngCertificates=false"  
/>  
  
```  
  
 Dies kann auch programmgesteuert mit dem Code durchgeführt werden, so wie in folgendem Beispiel gezeigt:  
  
```csharp  
  
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";  
AppContext.SetSwitch(disableCngCertificates, false);  
  
```  
  
```vb  
  
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"  
AppContext.SetSwitch(disableCngCertificates, False)  
  
```  
  
 **Bessere Unterstützung für mehrere Anpassungsregeln für die Sommerzeit, von der DataContractJsonSerializer-Klasse**  
 Kunden können eine anwendungseinstellung verwenden, um zu bestimmen, ob die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> Klasse unterstützt mehrere Anpassungsregeln einer Zeitzone. Dies ist ein Opt-in-Feature. Fügen Sie die folgende Einstellung der Datei app.config hinzu, um sie zu aktivieren:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 Wenn dieses Feature aktiviert ist, eine <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> -Objekt verwendet die <xref:System.TimeZoneInfo> -Typ statt der <xref:System.TimeZone> zu Datums-und Uhrzeitdaten zu deserialisierenden Typ. <xref:System.TimeZoneInfo> unterstützt mehrere Anpassungsregeln historisch Zeitzonendaten; arbeiten werden   <xref:System.TimeZone> nicht.  
  
 Weitere Informationen zu den <xref:System.TimeZoneInfo> Struktur und zeitzonenanpassungen, finden Sie unter [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).  
  
 **Unterstützung zur Beibehaltung von UTC-Uhrzeit serialisieren und Deserialisieren von mit der XMLSerializer-Klasse**  
 Normalerweise, wenn der <xref:System.Xml.Serialization.XmlSerializer> Klasse zum Serialisieren von UTC <xref:System.DateTime> Wert wird eine serialisierten Zeichenfolge, die beibehalten werden, das Datum und die Uhrzeit, sondern setzt voraus, die Zeit ist die lokale erstellt.  Wenn Sie beispielsweise ein UTC-Datum und eine UTC-Uhrzeit instanziieren, indem Sie den folgenden Code aufrufen:  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 ist das Ergebnis für ein System, das acht Stunden hinter der Zeitzone UTC ist, die serialisierten Zeit-Zeichenfolge „03:00:00.0000000-08:00“ .  Serialisierte Werte sind zudem immer als lokale Datums- und Uhrzeitwerte deserialisiert.  
  
 Können Sie eine Konfigurationseinstellung für die Anwendung um zu bestimmen, ob die <xref:System.Xml.Serialization.XmlSerializer> behält UTC-Zeitzone-Informationen beim Serialisieren und Deserialisieren von <xref:System.DateTime> Werte:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 Wenn dieses Feature aktiviert ist, eine <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> -Objekt verwendet die <xref:System.TimeZoneInfo> -Typ statt der <xref:System.TimeZone> zu Datums-und Uhrzeitdaten zu deserialisierenden Typ. <xref:System.TimeZoneInfo> unterstützt mehrere Anpassungsregeln historisch Zeitzonendaten; arbeiten werden   <xref:System.TimeZone> nicht.  
  
 Weitere Informationen zu den <xref:System.TimeZoneInfo> Struktur und zeitzonenanpassungen, finden Sie unter [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).  
  
 **NetNamedPipeBinding beste Übereinstimmung**  
 WCF bietet eine neue App-Einstellung, die für Clientanwendungen festgelegt werden kann, um sicherzustellen, dass diese immer eine Verbindung zu dem Dienst herstellen, der an dem URI lauscht, der die höchste Übereinstimmung zu dem aufweist, den die Anwendungen anfordern. Mit dieser app-Einstellung festgelegt `false` (Standard), es ist möglich, für Clients mit <xref:System.ServiceModel.NetNamedPipeBinding> zum Herstellen einer Verbindung mit einem Dienst überwacht ein URI, der eine Teilzeichenfolge der angeforderte URI ist.  
  
 Angenommen, ein Client versucht, eine Verbindung zu einem Dienst herzustellen, der an `net.pipe://localhost/Service1` lauscht, aber ein anderer Dienst auf dem Computer, der mit Administratorrechten ausgeführt wird, lauscht an `net.pipe://localhost`. Der Client würde versuchen, mit dieser App-Einstellung, die auf `false` festgelegt ist, eine Verbindung zu dem falschen Dienst herzustellen. Nach dem Festlegen der App-Einstellung auf `true`, wird der Client stets eine Verbindung zu den passendsten Dienst herstellen.  
  
> [!NOTE]
>  Clients mit <xref:System.ServiceModel.NetNamedPipeBinding> Dienste basierend auf die Basisadresse des Diensts (falls vorhanden) anstatt vollständige Endpunktadresse suchen. Damit diese Einstellung immer funktioniert muss der Dienst eine eindeutige Basisadresse verwenden.  
  
 Fügen Sie die folgende App-Einstellung der App.config- oder Web.config-Datei der Anwendung Ihres Clients hinzu, um die Änderung zu aktivieren:  
  
```xml  
  
<configuration>  
    <appSettings>  
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />  
    </appSettings>  
</configuration>  
  
```  
  
 **SSL 3.0 ist ein Standardprotokoll**  
 Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird SSL 3.0 nicht länger als eines der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet. In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 in der Protokollliste für NetTcp enthalten ist. Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln.      Wenn Ssl3 erforderlich ist, verwenden Sie eine der folgenden Konfigurationsmechanismen, um es der Liste der ausgehandelten Protokolle hinzuzufügen.  
  
-   Die <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> Eigenschaft  
  
-   Die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> Eigenschaft  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) section  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) section  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Windows Presentation Foundation in den folgenden Bereichen erweitert:  
  
 **Gruppe sortieren**  
 Eine Anwendung, verwendet eine <xref:System.Windows.Data.CollectionView> Objekt zum Gruppieren von Daten kann nun explizit deklarieren, wie die Gruppen zu sortieren. Das explizite Sortieren behebt das Problem der nicht-intuitiven Sortierung beim dynamischen Hinzufügen oder Entfernen von Gruppen und beim Ändern des Wert der beim Gruppieren beteiligten Elementeigenschaften durch eine App. Diese Vorgehensweise kann auch die Leistung des Gruppenerstellungsprozesses verbessern, indem Vergleiche der Gruppierungseigenschaften nicht bei der Sortierung der vollständigen Sammlung, sondern bei der Sortierung der Gruppen erfolgen/vorgenommen werden.  
  
 Zur Unterstützung der Gruppe sortieren, die neue <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=fullName> und <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=fullName> Eigenschaften beschrieben, wie Sie die Auflistung von Gruppen von erzeugten Sortieren der <xref:System.ComponentModel.GroupDescription> Objekt. Dies ist analog zu der gleichnamigen wie <xref:System.Windows.Data.ListCollectionView> Eigenschaften beschrieben, wie Sie die Datenelemente zu sortieren.  
  
 Zwei neue statische Eigenschaften der <xref:System.Windows.Data.PropertyGroupDescription> -Klasse, <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> und <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, für die am häufigsten vorkommenden Fälle verwendet werden kann.  
  
 Zum Beispiel gruppiert der folgende XAML-Code Daten nach Alter, sortiert die Gruppen in aufsteigender Reihenfolge und gruppierten die Elemente in den einzelnen Gruppen anhand des Nachnamens.  
  
```xaml  
  
<GroupDescriptions>  
     <PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     <SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **Bildschirmtastatur-Unterstützung**  
 Die Bildschirmtastatur-Unterstützung ermöglicht die fokussierte Verfolgung in WPF-Anwendungen, indem automatisch die neue Bildschirmtastatur in Windows 10 aufgerufen und geschlossen wird, wenn die Fingereingabe von einem Steuerelement empfangen wird, das Texteingabe nutzen kann.  
  
 In früheren Versionen des .NET-Frameworks konnte für WPF-Anwendungen die Fokusverfolgung nur aktiviert werden, wenn in WPF die Unterstützung für Stifte und Touchgesten deaktiviert wurde.  Die WPF-Anwendungen müssen daher zwischen der vollständiger WPF-Gestenunterstützung und der Windows-Mausheraufstufung wählen.  
  
 **DPI pro monitor**  
 Um die neueste Vervielfältigung von hohen DPI- und hybrider DPI-Umgebungen für WPF-Apps zu unterstützen, sorgt WPF dafür, dass monitorspezifische DPI-Werte in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] erkannt werden. Finden Sie unter der [Beispiele und Entwicklerhandbuch](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) auf GitHub für Weitere Informationen dazu, wie Sie die WPF-App zu pro-Monitor DPI-bewusst.  
  
 In früheren Versionen von .NET Framework sind WPF-Apps kompatibel mit systemspezifischen DPI-Werten. Die Benutzeroberfläche der Anwendung wird anders gesagt ggf. mit dem Betriebssystem skaliert, abhängig von der DPI des Monitors, auf dem die App gerendert wird. ,  
  
 Für apps, die unter der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Sie können Änderungen von DPI pro Monitor in WPF-apps deaktivieren, indem Sie eine Configuration-Anweisung, die [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Abschnitt der Anwendungskonfiguration Datei wie folgt:  
  
```xml  
  
<runtime>  
   <AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Windows Workflow Foundation im folgenden Bereich erweitert:  
  
 **Unterstützung für C#-Ausdrücke und IntelliSense im Re-hosted WF-Designer**  
 Beginnend mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], unterstützt WF C#-Ausdrücke sowohl im Visual Studio-Designer als auch in Codeworkflows. Der neu gehostete Workflow-Designer ist eine wichtige Funktion von WF, die zulässt, dass sich der Workflow-Designer in einer Anwendung außerhalb von Visual Studio befindet (z.B. in WPF).  Windows Workflow Foundation bietet die Möglichkeit der Unterstützung von C#-Ausdrücken und IntelliSense im neu gehosteten Workflow-Designer. Weitere Informationen finden Sie unter der [Windows Workflow Foundation-Blog](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 In Versionen von .NET Framework vor [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wird IntelliSense in WF-Designer unterbrochen, wenn ein Kunde eine Workflowprojekt von Visual Studio neu erstellt. Während der Projektbuild erfolgreich ist, die Workflowtypen im Designer nicht gefunden werden und Warnungen von IntelliSense für die fehlenden Workflowtypen, in angezeigt der **Fehlerliste** Fenster. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] behandelt dieses Problem und macht IntelliSense verfügbar.  
  
 **Workflow-V1-Clientanwendungen mit einem Workflow überwachen auf jetzt ausführen, im FIPS-Modus**  
 Computer mit aktiviertem FIPS-Kompatibilitätsmodus können jetzt erfolgreich eine Anwendung, die dem Stil der Workflowversion 1 entspricht, mit aktivierter Workflowüberwachung ausführen. Sie müssen die folgenden Änderungen in Ihrer app.config-Datei vornehmen, um dieses Szenario zu aktivieren:  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 Wenn dieses Szenario nicht aktiviert ist, führt das Ausführen der Anwendung weiterhin dazu, dass eine Ausnahme mit folgender Meldung ausgelöst wird: „Diese Implementation ist nicht Teil der Windows Platform FIPS-überprüften kryptografischen Algorithmen.“  
  
 **Workflow-Verbesserungen bei dynamischen Updates mit Visual Studio-Workflow-Designer**  
 Die Workflow-Designer, Flussdiagramm-Aktivitätsdesigner, und Workflow-Aktivitätsdesigner jetzt erfolgreich laden und Anzeigen von Workflows, die nach dem Aufruf gespeichert wurden die <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> Methode. In Versionen von .NET Framework vor der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], das Laden einer XAML-Datei in Visual Studio für einen Workflow, der nach dem Aufruf gespeichert wurde <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> kann dazu führen, dass die folgenden Probleme:  
  
-   Workflow-Designer kann nicht die XAML-Datei ordnungsgemäß geladen (bei der <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=fullName> befindet sich am Ende der Zeile).  
  
-   Der Flussdiagramm-Aktivitätsdesigner oder andere Workflow-Aktivitätsdesigner können möglicherweise alle Objekte an ihrem Standardspeicherort anzeigen, im Gegensatz zu angefügten Eigenschaftswerten.  
  
<a name="ClickOnce"></a>   
### <a name="clickonce"></a>ClickOnce  
 ClickOnce wurde zur Unterstützung von TLS 1.1 und TLS 1.2 neben dem 1.0-Protokoll aktualisiert, das schon unterstützt wird. ClickOnce erkennt automatisch, welches Protokoll erforderlich ist. Es sind keine zusätzlichen Schritte innerhalb der ClickOnce-Anwendung erforderlich, um die TLS 1.1 und 1.2-Unterstützung zu aktivieren.  
  
<a name="UWPConvert"></a>   
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Konvertieren von Windows Forms und WPF-Apps in UWP-Apps  
 Windows bietet nun Möglichkeiten, vorhandene Windows Desktop-Apps, einschließlich WPF- und Windows Forms-Apps, auf der Universal Windows Platform (UWP) bereitzustellen. Diese Technologie agiert als Brücke, indem sie Ihnen ermöglicht, Ihre vorhandene Codebasis nach und nach zu UWP zu migrieren und so Ihre App auf allen Windows 10-Geräten bereitzustellen.  
  
 Konvertierte Desktop-Apps erlangen eine App-Identität ähnlich der App-Identität von UWP-Apps, wodurch UWP-APIs zugänglich gemacht werden, um Funktionen wie Live-Kacheln und Benachrichtigungen zu aktivieren. Die App verhält sich weiterhin wie zuvor und wird als voll vertrauenswürdige App ausgeführt. Sobald die App konvertiert ist, kann ein App-Container-Prozess zum vorhandenen voll vertrauenswürdigen Prozess hinzugefügt werden, um eine adaptive Benutzeroberfläche hinzuzufügen. Wenn alle Funktionen in den App-Container-Prozess verschoben werden, kann der vollständig vertrauenswürdige Prozess entfernt werden, und die neue UWP-App kann auf allen Windows 10-Geräten zur Verfügung gestellt werden.  
  
<a name="Debug462"></a>   
### <a name="debugging-improvements"></a>Verbesserungen beim Debugging  
 Die *nicht verwalteten Debug-API* wurde verbessert, der [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] zusätzlichen Analysen durchführen bei einer <xref:System.NullReferenceException> wird ausgelöst, sodass es möglich ist, zu bestimmen, welche Variablen in einer einzelnen Zeile des Quellcodes ist `null`.   Um dieses Szenario zu unterstützen, wurden die folgenden APIs der nicht verwalteten Debug-API hinzugefügt.  
  
-   Die [ICorDebugCode4](../../../ocs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md), und [ICorDebugVariableHomeEnum](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) Schnittstellen, die den systemeigenen Häuser verwaltete Variablen verfügbar zu machen. Dadurch Debuggern bereitgestellt werden, führen Sie einige Datenfluss Codeanalyse bei einer <xref:System.NullReferenceException> tritt auf, und Abwärtskompatibilität arbeiten, um die verwaltete Variablen zu bestimmen, die den systemeigenen Speicherort entspricht, die `null`.  
  
-   Die [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) Methode bietet eine Zuordnung für ICorDebugType auf [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md), die ermöglicht es dem Debugger zum Abrufen einer [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) ohne eine Instanz der ICorDebugType. Vorhandenen APIs auf [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) kann dann verwendet werden, um das Klassenlayout des Typs zu bestimmen.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>Neuigkeiten in .NET Framework 4.6.1  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] enthält neue Features in den folgenden Bereichen:  
  
-   [Kryptografie](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [Profilerstellungstools](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 Weitere Informationen zu [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] finden Sie unter den folgenden Themen:  
  
-   Die [.NET Framework 4.6.1 Liste der Änderungen](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)  
  
-   [Die .NET Framework-API-Unterschiede](http://go.microsoft.com/fwlink/?LinkId=622989) (unter GitHub)  
  
<a name="Crypto"></a>   
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Kryptografie: Unterstützung für X509-Zertifikate mit ECDSA  
 RSACng-Unterstützung für X509-Zertifikate in .NET Framework 4.6. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] fügt Unterstützung für ECDSA (Elliptic Curve Digital Signature Algorithm) X509-Zertifikate hinzu.  
  
 ECDSA bietet eine bessere Leistung und einen sichereren Kryptografiealgorithmus als RSA. Somit ist die Lösung eine hervorragende Wahl, wenn es um TLS (Transport Layer Security)-Leistung und Skalierbarkeit geht. Die .NET Framework-Implementierung schließt Aufrufe in die vorhandene Windows-Funktionalität ein.  
  
 Im folgenden Codebeispiel wird gezeigt, wie einfach es ist, eine Signatur für einen Bytedatenstrom mit der neuen in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] enthaltenen ECDSA-Unterstützung für X509-Zertifikate zu generieren.  
  
 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
 [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]  
  
 Dies steht in deutlichem Gegensatz zu dem Code, der zum Generieren einer Signatur in .NET Framework 4.6 erforderlich war.  
  
 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
 [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]  
  
<a name="ADO.NET461"></a>   
### <a name="adonet"></a>ADO.NET  
 ADO.NET wurde um die folgenden Features erweitert:  
  
 "Always Encrypted"-Unterstützung für hardwaregeschützte Schlüssel  
 ADO.NET unterstützt jetzt die systemeigene Speicherung von "Always Encrypted"-Spaltenhauptschlüsseln in Hardwaresicherheitsmodulen (Hardware Security Modules, HSMs). Mit dieser Unterstützung profitieren Kunden von asymmetrischen, in HSMs gespeicherten Schlüsseln, ohne benutzerdefinierte Spaltenhauptschlüssel-Speicheranbieter zu schreiben und in Anwendungen registrieren zu müssen.  
  
 Kunden müssen die vom HSM-Anbieter bereitgestellten CSP-Anbieter oder CNG-Schlüsselspeicheranbieter auf den App-Servern oder Clientcomputern installieren, um über die in einem HSM gespeicherten Spaltenhauptschlüssel auf die mit "Always Encrypted" geschützten Daten zuzugreifen.  
  
 Verbesserung der <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> Verbindungsverhalten für AlwaysOn  
 SqlClient ermöglicht jetzt automatisch schnellere Verbindungen mit einer AlwaysOn-Verfügbarkeitsgruppe (Availability Group, AG). Er erkennt auf transparente Weise, ob die Anwendung eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe in einem anderen Subnetz herstellt, ermittelt schnell den aktiven Server und stellt eine Verbindung mit dem Server her. Vor dieser Version musste eine Anwendung `“MultisubnetFailover=true”` in die Verbindungszeichenfolge einschließen, um anzugeben, dass eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe hergestellt wurde. Wenn das Verbindungsschlüsselwort nicht auf `true` festgelegt wird, kann bei der Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe ein Anwendungstimeout auftreten. Mit dieser Version eine Anwendung ist *nicht* müssen <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> auf `true` nicht mehr. Weitere Informationen zu SqlClient-Unterstützung für AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [SqlClient Support for High Availability, Disaster Recovery](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 Windows Presentation Foundation umfasst eine Reihe von Verbesserungen und Änderungen.  
  
 Leistungssteigerung  
 Die Verzögerung beim Auslösen von Touchereignissen wurde in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] behoben. Darüber hinaus geben Sie in einem <xref:System.Windows.Controls.RichTextBox> Steuerelement der Render-Thread nicht mehr während der schnellen Eingabe verknüpft.  
  
 Verbesserte Rechtschreibprüfung  
 Die Rechtschreibprüfung in WPF wurde unter Windows 8.1 und höheren Versionen aktualisiert, um die Betriebssystemunterstützung für die Rechtschreibprüfung zusätzlicher Sprachen zu nutzen.  Bezüglich der Funktionalität in Windows-Versionen vor Windows 8.1 gibt es keine Änderung.  
  
 Wie in früheren Versionen von .NET Framework, die Sprache für eine <xref:System.Windows.Controls.TextBox> steuern Ora <xref:System.Windows.Controls.RichTextBox> Block wird anhand der Informationen in der folgenden Reihenfolge ermittelt:  
  
-   `xml:lang`, falls vorhanden.  
  
-   Aktuelle Eingabesprache  
  
-   Aktuelle Threadkultur  
  
 Weitere Informationen zur sprachunterstützung von in WPF finden Sie unter der [WPF-Blog-Beitrag zu den Features von .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).  
  
 Zusätzliche Unterstützung für benutzerdefinierte Wörterbücher pro Benutzer  
 In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] erkennt WPF benutzerdefinierte Wörterbücher, die global registriert sind. Diese Funktion ist zusätzlich zur Registrierung der Wörterbücher pro Steuerelement verfügbar.  
  
 In früheren WPF-Versionen wurden Listen ausgeschlossener Wörter und AutoKorrektur-Listen von benutzerdefinierten Wörterbüchern nicht erkannt. Diese werden unter Windows 8.1 und Windows 10 mittels Dateien unterstützt, die im Verzeichnis `%AppData%\Microsoft\Spelling\<language tag>` abgelegt werden können.  Für diese Dateien gelten die folgenden Regeln:  
  
-   Die Dateien sollten über die Erweiterungen ".dic" (hinzugefügte Wörter), ".exc" (ausgeschlossene Wörter) oder ".acl" (AutoKorrektur-Wörter) verfügen.  
  
-   Außerdem sollten sie das UTF-16LE-Nur-Text-Format aufweisen, das mit der Bytereihenfolgenmarke (Byte Order Mark, BOM) beginnt.  
  
-   Jede Zeile sollte ein Wort (in der hinzugefügten und ausgeschlossenen Wortlisten) bestehen oder ein AutoKorrektur-Paar mit den Wörtern getrennt durch einen senkrechten Strich ("|") (in der AutoKorrektur-Liste).  
  
-   Diese Dateien sind schreibgeschützt und werden vom System nicht geändert.  
  
> [!NOTE]
>  Diese neuen Dateiformate werden von der WPF-Rechtschreibprüfungs-API nicht direkt unterstützt, sodass die benutzerdefinierten Wörterbücher, die in Anwendungen für WPF bereitgestellt werden, weiterhin LEX-Dateien verwenden sollten.  
  
 Proben  
 Es gibt eine Reihe von [WPF-Beispiele](https://msdn.microsoft.com/library/ms771633.aspx) auf MSDN. Werden mehr als 200 der am häufigsten verwendeten Beispiele (basierend auf ihrer Verwendung) verschoben, in einer [Open Source-GitHub-Repository](https://github.com/Microsoft/WPF-Samples). Helfen Sie uns, unsere Beispiele zu verbessern, indem Sie senden uns eine Pull-Anforderung oder Öffnen einer [GitHub Problem](https://github.com/Microsoft/WPF-Samples/issues).  
  
 DirectX-Erweiterungen  
 WPF enthält eine [NuGet-Paket](http://go.microsoft.com/fwlink/?LinkID=691342) , die bietet die neue Implementierung von <xref:System.Windows.Interop.D3DImage> , mit denen Sie für die Zusammenarbeit mit DX10 und Dx11 Inhalt. Der Code für dieses Paket geöffnet wurde bezogen und steht [auf GitHub](https://github.com/Microsoft/WPFDXInterop).  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Transaktionen  
 Die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> Methode können nun einen verteilten Transaktions-Managers als MS DTC die Transaktion höher gestuft. Sie dazu eine Transaktion Projektträger-GUID der neuen <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> überladen. Wenn dieser Vorgang erfolgreich ist, unterliegt die Transaktionsfunktionalität gewissen Einschränkungen. Sobald Projektträger eine nicht-MS-DTC-Transaktion eingetragen ist, löst die folgenden Methoden eine <xref:System.Transactions.TransactionPromotionException> , da diese Methoden zu MS DTC heraufgestuft erfordern:  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=fullName>  
  
 Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, muss er mit dauerhaften Eintragungen verwendet werden. Dabei werden die von ihm definierten Protokolle verwendet. Die <xref:System.Guid> der Transaktion Projektträger abgerufen werden kann, mithilfe der <xref:System.Transactions.Transaction.PromoterType%2A> Eigenschaft. Wenn die Transaktion fördert, die Transaktion Projektträger bietet ein <xref:System.Byte> Array, das höher gestufte Token darstellt. Eine Anwendung kann die höher gestuften Token für eine Transaktion MSDTC nicht höher gestuft mit Abrufen der <xref:System.Transactions.Transaction.GetPromotedToken%2A> Methode.  
  
 Benutzer des neuen <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> Überladung muss eine bestimmte Aufruffolge in der Reihenfolge für das Heraufstufen erfolgreich abgeschlossen. Diese Regeln werden in der Dokumentation der Methode beschrieben.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>Profilerstellung  
 Die nicht verwaltete Profilerstellungs-API wurde wie folgt erweitert:  
  
 Bessere Unterstützung für den Zugriff auf die PDB-Dateien in den [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) Schnittstelle  
 In ASP.Net 5 werden Assemblys im Arbeitsspeicher immer häufiger mit Roslyn kompiliert. Für Entwickler von Profilertools bedeutet dies, dass PDB-Dateien, die früher auf Datenträgern serialisiert wurden, u. U. nicht mehr vorkommen. Profilertools verwenden PDB-Dateien häufig, um Codezeilen wieder den Quellzeilen zuzuordnen, beispielsweise für die Codeabdeckung oder zeilenweise Leistungsanalysen. Die [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) Schnittstelle enthält nun zwei neue Methoden [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) und [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), bereitzustellen, diese Profilerbefehlszeilentools mit Zugriff auf die PDB-Daten im Arbeitsspeicher mithilfe der neuen APIs ein Profiler kann erhalten Sie den Inhalt einer PDB im Arbeitsspeicher als Bytearray und dann verarbeiten oder auf der Festplatte zu serialisieren.  
  
 Bessere Instrumentation mit der ICorProfiler-Schnittstelle  
 Profiler, die die ReJit-Funktionalität der `ICorProfiler`-API für die dynamische Instrumentation verwenden, sind jetzt in der Lage, einige Metadaten zu ändern. Früher konnte IL durch diese Tools jederzeit instrumentiert werden, während Metadaten nur zur Ladezeit des Moduls geändert werden konnten. Da IL auf Metadaten verweist, sind die möglichen Instrumentationsarten eingeschränkt. Wir haben einige dieser Grenzwerte transformiert, durch Hinzufügen der [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md) -Methode unterstützt eine Teilmenge der Metadaten, nachdem das Modul, insbesondere lädt durch Hinzufügen neuer `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec`, und `UserString` Datensätze. Diese Änderung erweitert die Möglichkeiten der dynamischen Instrumentation.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>NGEN (Native Image Generator)-PDBs  
 Die computerübergreifende Ereignisablaufverfolgung ermöglicht Kunden die Profilerstellung für ein Programm auf Computer A und die Anzeige der Profilerstellungsdaten per Quellzeilenzuordnung auf Computer B. Unter früheren .NET Framework-Versionen musste der Benutzer alle Module und systemeigenen Images vom Profilcomputer auf den Analysecomputer kopieren, der die IL PDB-Datei für die Zuordnung zwischen Quellzeilen und systemeigenen Images enthielt. Während dies bei kleineren Dateien wie Handy-Apps durchaus gut funktionieren kann, können Desktopsystemdateien ziemlich anwachsen und beträchtliche Zeit für das Kopieren erfordern.  
  
 Bei NGEN PDB-Dateien kann NGen eine PDB-Datei erstellen, die die Zuordnung zwischen IL und systemeigenen Images enthält, ohne dass eine Abhängigkeit von der IL PDB-Datei besteht. In diesem Szenario computerübergreifend Event Tracing erforderlich ist, ist das systemeigene Abbild PDB-Datei zu kopieren, der von Computer A mit Computer B generiert und verwendet [Debuggen-Schnittstelle Zugriff APIs](https://msdn.microsoft.com/en-us/library/ee8x173s.aspx) zum Lesen der IL-PDB-Quelle-zu-IL-Zuordnung und die systemeigene Images PDB IL-Code und systemeigenem Zuordnung. Durch die Kombination beider Zuordnungen entsteht eine Zuordnung zwischen Quellzeilen und systemeigenem Image. Da die PDB-Datei für systemeigene Images viel kleiner als alle Module und systemeigenen Images ist, wird das Kopieren von Computer A auf Computer B deutlich beschleunigt.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>Neuigkeiten in .NET 2015  
 In .NET 2015 werden [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und .NET Core eingeführt. Einige neue Funktionen gelten für beide, während andere Funktionen für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] bzw. [!INCLUDE[net_core](../../../includes/net-core-md.md)] spezifisch sind.  
  
-   **ASP.NET 5**  
  
     .NET 2015 enthält ASP.NET 5, eine schlanke .NET-Plattform zum Erstellen moderner, cloudbasierter Apps. Die Plattform ist modular aufgebaut, sodass Sie nur die Funktionen aufnehmen können, die Sie in Ihrer Anwendung benötigen. Sie kann auf IIS oder eigenständig in einem benutzerdefinierten Prozess gehostet werden, und Sie können Apps mit verschiedenen Versionen von .NET Framework auf demselben Server ausführen. Sie umfasst ein neues Umgebungskonfigurationssystem, das für die Cloudbereitstellung entwickelt wurde.  
  
     MVC, Web-API und Webseiten sind in einem einzigen Framework namens MVC 6 vereint. Sie erstellen ASP.NET 5-Apps mithilfe der neuen Tools in Visual Studio 2015. Ihre vorhandenen Anwendungen funktionieren im neuen .NET Framework. Um jedoch eine App zu erstellen, die MVC 6 oder SignalR 3 verwendet, müssen Sie das Projektsystem in Visual Studio 2015 verwenden.  
  
     Weitere Informationen finden Sie unter [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).  
  
-   **Updates für ASP.NET**  
  
    -   **Task-basierte API für die asynchrone Antwort leeren**  
  
         ASP.NET bietet nun eine einfache Aufgabe-basierte API für das asynchrone Antwort zu leeren, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=fullName>, mit der Antworten asynchron geleert werden, mit der Sprache `async/await` unterstützen.  
  
    -   `Model binding supports task-returning methods`  
  
         In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], ASP.NET wurde das Modellbindungsfeature hinzugefügt, das einen erweiterbaren, codeorientierten Ansatz für CRUD-basierte Datenvorgänge in Web Forms-Seiten und Benutzersteuerelementen ermöglicht. Das Modell Bindungssystem unterstützt jetzt <xref:System.Threading.Tasks.Task>-Modell Bindung Methoden zurückgeben. Dadurch erhalten Web Forms-Entwickler die Vorteile hinsichtlich der Asynchronität und die Einfachheit des Datenbindungssystems beim Verwenden neuerer Versionen von ORMs, einschließlich des Entity Frameworks.  
  
         Die asynchrone Modellbindung wird durch die `aspnet:EnableAsyncModelBinding`-Konfigurationseinstellung gesteuert.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         Bei auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielenden Apps wird der Standardwert auf `true` festgelegt. Bei Apps unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], die auf eine frühere Version von .NET Framework abzielen, ist `false` der Standard. Dies kann aktiviert werden, indem die Konfigurationseinstellung auf `true` festgelegt wird.  
  
    -   **HTTP/2-Unterstützung (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) ist eine neue Version des HTTP-Protokolls, die bietet wesentlich bessere Nutzung von Verbindungen (weniger Roundtrips zwischen Client und Server), was zu Latenz Webseiten für Benutzer laden.  Webseiten profitieren am meisten von HTTP/2 (im Gegensatz zu Services), da das Protokoll Anforderungen mehrerer Artefakte in einem Aufruf zusammenfasst und so optimiert. Die HTTP/2-Unterstützung wurde zu ASP.NET in .NET Framework 4.6 hinzugefügt. Da Netzwerkfunktionen auf mehreren Ebenen vorhanden sind, waren neue Funktionen in Windows, IIS und ASP.NET erforderlich, um HTTP/2 nutzen zu können. Sie müssen Windows 10 ausführen, um HTTP/2 mit ASP.NET nutzen zu können.  
  
         HTTP/2 wird ebenfalls unterstützt und auf standardmäßig für Windows 10 universelle Windows-Plattform (UWP) apps, die die <xref:System.Net.Http.HttpClient?displayProperty=fullName> API.  
  
         Um die Möglichkeit, verwenden Sie die [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) -Features in ASP.NET Applications, eine neue Methode mit zwei Überladungen <xref:System.Web.HttpResponse.PushPromise%28System.String%29> und <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, hinzugefügt wurde der <xref:System.Web.HttpResponse> Klasse.  
  
        > [!NOTE]
        >  Während ASP.NET 5 Unterstützung für HTTP/2 enthält, wurde noch keine Unterstützung für das PUSH PROMISE-Feature hinzugefügt.  
  
         Browser und Webserver (IIS unter Windows) erledigen die gesamte Arbeit. Sie müssen keine umfangreichen Aufgaben für Ihre Benutzer ausführen.  
  
         Die meisten der [wichtigen Browser unterstützen HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), daher ist es wahrscheinlich, dass Ihre Benutzer über HTTP/2-Unterstützung profitieren können, wenn Ihr Server es unterstützt.  
  
    -   **Unterstützung für das Tokenbindungsprotokoll**  
  
         Microsoft und Google haben einen neuen Ansatz für Authentifizierung, genannt Zusammenarbeit der [Tokenbindungsprotokoll](https://github.com/TokenBinding/Internet-Drafts). Voraussetzung ist, dass die Authentifizierungstoken (in Ihrem Browsercache) gestohlen und von Kriminellen ansonsten sicheren Zugriff auf die Ressourcen (z. B. Ihr Bankkonto) ohne Ihr Kennwort oder andere geschützte Informationen verwendet werden können. Das neue Protokoll zielt darauf ab, dieses Problem zu minimieren.  
  
         Das Tokenbindungsprotokoll wird in Windows 10 als Browserfunktion implementiert. ASP.NET-Anwendungen werden in das Protokoll einbezogen, damit die Legitimität von Authentifizierungstoken überprüft werden kann. Die Client- und Serverimplementierungen stellen den durch das Protokoll angegebenen umfassenden Schutz bereit.  
  
    -   **Zufällige Zeichenfolge Hash-Algorithmen**  
  
         .NET Framework 4.5 eingeführte ein [zufällige Zeichenfolge Hashalgorithmus](https://msdn.microsoft.com/library/jj152924.aspx). Dieser wurde jedoch durch ASP.NET nicht unterstützt, da einige der ASP.NET von einem stabilen Hash abhängig sind. In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] werden nun zufällige Zeichenfolgen-Hashalgorithmen unterstützt. Verwenden Sie zum Aktivieren dieses Features die `aspnet:UseRandomizedStringHashAlgorithm`-Konfigurationseinstellung.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET unterstützt jetzt das in SQL Server 2016 Community Technology Preview 2 (CTP2) verfügbare Feature zum grundsätzlichen Verschlüsseln. Mit der grundsätzlichen Verschlüsselung kann SQL Server Operationen zu verschlüsselten Daten durchführen und das Beste ist, der Verschlüsselungsschlüssel ist bei der Anwendung in der vertrauenswürdigen Umgebung des Kunden abgelegt, nicht auf dem Server. Die grundsätzliche Verschlüsselung sichert Kundendaten so, dass DBAs keinen Zugriff auf Textdaten haben. Die Verschlüsselung und Entschlüsselung von Daten erfolgt transparent auf Treiberebene, dadurch werden die an vorhandenen Anwendungen erforderlichen Änderungen auf ein Mindestmaß reduziert. Weitere Informationen finden Sie unter [immer verschlüsselt (Datenbankmodul)](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) und [immer verschlüsselt (Entwicklung)](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx).  
  
-   **64-Bit-JIT-Compiler für verwalteten code**  
  
     .NET Framework 4.6 umfasst eine neue Version des 64-Bit-JIT-Compilers (ursprünglicher Codename „RyuJIT“). Der neue 64-Bit-Compiler bietet erhebliche Leistungsverbesserungen im Vergleich zum älteren 64-Bit-JIT-Compiler. Der neue 64-Bit-Compiler wird für 64-Bit-Prozesse aktiviert, die zusätzlich zu .NET Framework 4.6 ausgeführt werden. Ihre App wird in einem 64-Bit-Prozess ausgeführt, wenn sie als 64 Bit oder AnyCPU kompiliert ist und auf einem 64-Bit-Betriebssystem ausgeführt wird. Obwohl der Übergang zum neuen Compiler so transparent wie möglich verlief, sind Änderungen im Verhalten möglich. Wir möchten Sie bitten, uns direkt über Probleme zu informieren, die beim Verwenden des neuen JIT-Compilers auftreten. Wenden Sie sich an uns über [Microsoft Connect](http://connect.microsoft.com/) , wenn ein Problem auftritt, die mit der neuen 64-Bit-JIT-Compiler verknüpft werden kann.  
  
     Der neue 64-Bit-JIT-Compiler enthält auch SIMD Hardwarebeschleunigungsfunktionen mit SIMD-fähige Typen in der <xref:System.Numerics> -Namespace, die gute Leistungssteigerungen ergeben kann.  
  
-   **Verbesserungen am assemblylader**  
  
     Das Assemblyladeprogramm verwendet nun den Arbeitsspeicher effizienter, indem IL-Assemblys entladen werden, nachdem ein entsprechendes NGEN-Image geladen wurde. Durch diese Änderung wird der virtuelle Arbeitsspeicher verringert. Dies ist besonders bei großen 32-Bit-Apps (wie Visual Studio) hilfreich. Zudem wird dadurch physischer Arbeitsspeicher eingespart.  
  
-   **Änderungen an Basisklassenbibliotheken**  
  
     Viele neue APIs wurden im Umfeld von [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] hinzugefügt, um wichtige Szenarios zu ermöglichen. Dazu zählen die folgenden Änderungen und Ergänzungen:  
  
    -   **IReadOnlyCollection<> \</> \> Implementierungen**  
  
         Zusätzliche Auflistungen implementieren <xref:System.Collections.Generic.IReadOnlyCollection%601> wie z. B. <xref:System.Collections.Generic.Queue%601> und <xref:System.Collections.Generic.Stack%601>.  
  
    -   **CultureInfo.CurrentCulture und CultureInfo.CurrentUICulture**  
  
         Die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> Eigenschaften sind jetzt Schreib-/ statt schreibgeschützt. Wenn Sie ein neues zuweisen <xref:System.Globalization.CultureInfo> Objekt auf diese Eigenschaften der aktuellen Threadkultur definiert die `Thread.CurrentThread.CurrentCulture` -Eigenschaft und die aktuelle UI-Threadkultur definiert die `Thread.CurrentThread.CurrentUICulture` ändern sich ebenfalls.  
  
    -   **Verbesserte Garbagecollection (GC)**  
  
         Die <xref:System.GC> -Klasse enthält nun <xref:System.GC.TryStartNoGCRegion%2A> und <xref:System.GC.EndNoGCRegion%2A> Methoden, die Ihnen ermöglichen, Garbagecollection während der Ausführung eines kritischen Pfads zu unterbinden.  
  
         Eine neue Überladung der <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=fullName> Methode können Sie steuern, ob den kleinen Objektheap und der große Objektheap eine Komprimierung und komprimiert oder nur eine Komprimierung.  
  
    -   **SIMD-fähige Typen**  
  
         Die <xref:System.Numerics> Namespace enthält nun eine Reihe von SIMD-fähigen Datentypen wie z. B. <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, und <xref:System.Numerics.Vector4>.  
  
         Da der neue 64-Bit-JIT-Compiler zudem Hardware-SIMD-Beschleunigungsfeatures enthält, liegen insbesondere erhebliche Leistungsverbesserungen beim Verwenden von SIMD-fähigen Typen mit dem neuen 64-Bit-JIT-Compiler vor.  
  
    -   **Kryptografieupdates**  
  
         Die <xref:System.Security.Cryptography?displayProperty=fullName> API wird aktualisiert, um die Unterstützung der [Windows CNG-Kryptografie-APIs](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Frühere Versionen von .NET Framework haben völlig auf verlassen ein [frühere Version der Windows-Kryptografie-APIs](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) als Grundlage für die <xref:System.Security.Cryptography?displayProperty=fullName> Implementierung. Wir hatten die CNG-API, Unterstützung, da er unterstützt [moderne Kryptografiealgorithmen](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), die für bestimmte Kategorien von apps wichtig sind.  
  
         .NET Framework 4.6 umfasst die folgenden neuen Erweiterungen, um die Kryptografie-API von Windows CNG zu unterstützen:  
  
        -   Ein Satz von Erweiterungsmethoden für X509-Zertifikate, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` und `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, die nach Möglichkeit anstelle einer CAPI-basierten Implementierung eine CNG-basierte Implementierung zurückgeben. (Für einige Smartcards usw. ist weiterhin CAPI erforderlich, und die APIs verarbeiten den Fallback).  
  
        -   Die <xref:System.Security.Cryptography.RSACng?displayProperty=fullName> -Klasse, die eine CNG-Implementierung des RSA-Algorithmus bietet.  
  
        -   Erweiterungen an der RSA-API, damit für allgemeine Aktionen keine Umwandlung mehr erforderlich ist. Z. B. Verschlüsseln von Daten mithilfe einer <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> Objekt erfordert Code wie den folgenden in früheren Versionen von .NET Framework.  
  
             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]  
  
             Code, der die neuen Kryptografie-APIs in .NET Framework 4.6 verwendet, kann wie folgt umgeschrieben werden, um die Umwandlung zu vermeiden.  
  
             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]  
  
    -   **Unterstützung für das Konvertieren von Datums- und Zeitangaben zu oder von Unix-Zeit**  
  
         Die folgenden neuen Methoden hinzugefügt wurden die <xref:System.DateTimeOffset> -Struktur zur Unterstützung der Konvertierung von Datums-und Uhrzeitwerte zu oder von Unix-Zeit:  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
    -   **Kompatibilitätsoptionen**  
  
         Die neue <xref:System.AppContext> Klasse fügt eine neue Kompatibilitätsfunktion, die es Autoren von Bibliotheken ermöglicht, die ihren Benutzern eine einheitliche abwahlmechanismus für neue Funktionalitäten bereitzustellen. Sie richtet einen lose gekoppelten Vertrag zwischen den Komponenten ein, um eine Anforderung zur Abwahl zu übermitteln. Diese Möglichkeit ist in der Regel wichtig, wenn vorhandene Funktionalitäten verändert werden. Im Gegensatz dazu existiert bereits eine implizite Auswahloption für neue Funktionalitäten.  
  
         Mit <xref:System.AppContext>definieren Bibliotheken und Kompatibilitätsschalter verfügbar machen, während Code, der davon abhängig, diese Optionen beeinflussen das Verhalten der Bibliothek festgelegt werden können. Standardmäßig stellen Bibliotheken die neue Funktionalität bereit. Nur wenn die Option festgelegt ist, stellen sie die vorherige Funktionalität bereit.  
  
         Eine Anwendung (oder eine Bibliothek) kann den Wert eines Schalters deklarieren (Dies ist immer ein <xref:System.Boolean> Wert), die einer abhängige Bibliothek definiert. Die Option ist immer implizit `false`. Durch Festlegen der Option auf `true` wird diese aktiviert. Durch explizites Festlegen der Option auf `false` wird das neue Verhalten aktiviert.  
  
        ```csharp  
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);  
        ```  
  
         Die Bibliothek muss überprüfen, ob ein Consumer den Wert der Option deklariert hat, und dann entsprechend reagieren.  
  
        ```  
  
        if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))   
        {  
           // This is the case where the switch value was not set by the application.   
           // The library can choose to get the value of shouldThrow by other means.   
           // If no overrides nor default values are specified, the value should be 'false'.   
           // A false value implies the latest behavior.  
        }  
  
           // The library can use the value of shouldThrow to throw exceptions or not.  
           if (shouldThrow)   
           {  
              // old code  
           }  
           else {  
              // new code  
           }  
        }  
  
        ```  
  
         Es empfiehlt sich, ein konsistentes Format für Optionen zu verwenden, da es sich hierbei um eine formellen Vertrag handelt, der von einer Bibliothek verfügbar gemacht wird. Das folgende Beispiel zeigt zwei offensichtliche Formate.  
  
        -   *Switch*.* Namespace*.* SwitchName*  
  
        -   *Switch*.* library*.* SwitchName*  
  
    -   **Änderungen an das aufgabenbasierte asynchrone Muster (TAP)**  
  
         Für apps, die als Ziel der [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> Objekte erben, die Kultur und die UI-Kultur des aufrufenden Threads. Das Verhalten von Apps, die mit früheren Versionen von .NET Framework arbeiten oder auf keine bestimmte Version von .NET Framework ausgelegt sind, ist davon nicht betroffen. Weitere Informationen finden Sie im Abschnitt "Kultur und aufgabenbasierte asynchrone Vorgänge" von der <xref:System.Globalization.CultureInfo> Thema-Klasse.  
  
         Die <xref:System.Threading.AsyncLocal%601?displayProperty=fullName> Klasse können Sie Umgebungsdaten dar, die für eine angegebene asynchrone ablaufsteuerung lokal ist, wie z. B. ein `async` Methode. Sie kann zum threadübergreifenden Beibehalten von Daten verwendet werden. Sie können auch eine Rückrufmethode, die benachrichtigt wird, wenn Umgebungsdaten entweder weil ändert definieren die <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=fullName> Eigenschaft wurde explizit geändert werden, oder weil der Thread einen Übergang Kontext gefunden.  
  
         Drei Hilfsmethoden, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=fullName>, und <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=fullName>, das aufgabenbasierte asynchrone Muster (TAP) abgeschlossene Aufgaben in einem bestimmten Zustand zurückgegeben wurde.  
  
         Die <xref:System.IO.Pipes.NamedPipeClientStream> Klasse unterstützt jetzt die asynchronen Kommunikation mit neuen <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. -Methode.  
  
    -   **EventSource unterstützt jetzt das Schreiben in das Ereignisprotokoll**  
  
         Jetzt können Sie die <xref:System.Diagnostics.Tracing.EventSource> Klasse anmelden Betrieb oder Verwaltung von Nachrichten in das Ereignisprotokoll außerdem auf eine beliebige vorhandenen ETW-Sitzungen auf dem Computer. Früher mussten Sie das „Microsoft.Diagnostics.Tracing.EventSource“-NuGet-Paket für diese Funktionalität verwenden. Diese Funktionalität ist nun in .NET Framework 4.6 integriert.  
  
         Sowohl das NuGet-Paket als auch .NET Framework 4.6 wurden mit den folgenden Features aktualisiert:  
  
        -   **Dynamische Ereignisse**  
  
             Ermöglichen das „spontane“ Definieren von Ereignissen, und zwar ohne das Erstellen von Ereignismethoden.  
  
        -   **Rich-Nutzlasten**  
  
             Ermöglicht, dass speziell attributierte Klassen und Arrays sowie primitive Typen als eine Nutzlast übergeben werden.  
  
        -   **Das Aktivitätsprotokoll**  
  
             Löst Start- und Stoppereignisse aus, um Ereignisse zwischen ihnen mit einer ID zu kennzeichnen, die alle aktuell aktiven Aktivitäten darstellt.  
  
         Auf diese unterstützen Funktionen, die überladene <xref:System.Diagnostics.Tracing.EventSource.Write%2A> Methode hinzugefügt wurde der <xref:System.Diagnostics.Tracing.EventSource> Klasse.  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **Verbesserte anzeigen**  
  
         Die HDPI-Unterstützung in WPF ist nun besser in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Es wurden Änderungen an der Layoutglättung vorgenommen, um die Instanzen von Clipping in Steuerelementen mit Begrenzungen zu reduzieren. Diese Funktion ist standardmäßig aktiviert, nur, wenn Ihre <xref:System.Runtime.Versioning.TargetFrameworkAttribute> für .NET 4.6 festgelegt ist.  Clientanwendungen, die frühere Versionen des Frameworks abzielen, jedoch ausgeführt werden, auf der [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] können das neue Verhalten entscheiden, indem Sie die folgende Zeile hinzufügen der [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) -Abschnitt der Datei "App.config":  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         Sich auf mehrere Monitore erstreckende WPF-Fenster mit unterschiedlichen DPI-Einstellungen (Multi-DPI-Einrichtung) wurden nun vollständig gerendert, und zwar ohne verdunkelte Bereiche. Sie können dieses Verhalten deaktivieren, indem Sie die folgende Zeile zum `<appSettings>`-Abschnitt der Datei „app.config“ hinzufügen, um dieses neue Verhalten zu deaktivieren:  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         Unterstützung für das automatische Laden von den Cursor nach rechts basierend auf DPI-Einstellung hinzugefügt wurde <xref:System.Windows.Input.Cursor?displayProperty=fullName>.  
  
    -   **Touch ist besser**  
  
         Der Kunde meldet sich auf [verbinden](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) , die touch erzeugt zu unvorhersehbarem Verhalten in behandelt wurden die [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Der Schwellenwert für das Doppeltippen für Windows Store- und WPF-Anwendungen entspricht nun dem in Windows 8.1 und höher.  
  
    -   **Unterstützung für transparente untergeordnete Fenster**  
  
         WPF in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] unterstützte transparente untergeordnete Fenster in Windows 8.1 und höher. Dadurch können Sie untergeordnete Fenster, die weder viereckig noch transparent sind, in Ihren Fenstern auf oberster Ebene erstellen. Sie können dieses Feature aktivieren, durch Festlegen der <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=fullName> -Eigenschaft `true`.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **SSL-Unterstützung**  
  
         WCF unterstützt nun SSL Version TLS 1.1 und TLS 1.2 neben SSL 3.0 und TLS 1.0 beim Verwenden von NetTcp mit Transportsicherheit und Clientauthentifizierung. Es ist nun möglich, auszuwählen, welches Protokoll verwendet werden soll, oder ältere und zugleich unsicherere Protokolle zu deaktivieren. Dies erreichen Sie durch Festlegen der <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> Eigenschaft oder indem Sie Folgendes in eine Konfigurationsdatei hinzufügen.  
  
        ```  
        <netTcpBinding>  
           <binding>  
              <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                 <transport clientCredentialType="None|Windows|Certificate"  
                            protectionLevel="None|Sign|EncryptAndSign"  
                            sslProtocols="Ssl3|Tls1|Tls11|Tls12">  
                    </transport>  
              </security>  
           </binding>  
        </netTcpBinding>  
  
        ```  
  
    -   **Senden von Nachrichten, die mit anderen HTTP-Verbindungen**  
  
         WCF ermöglicht Benutzern nun, sicherzustellen, dass bestimmte Nachrichten unter Verwendung von zugrunde liegenden HTTP-Verbindungen gesendet wurden. Hierfür gibt es zwei Möglichkeiten:  
  
        -   **Verwenden ein Präfix Gruppe Verbindung**  
  
             Benutzer können eine Zeichenfolge angeben, die WCF als ein Präfix für den Verbindungsgruppennamen verwendet. Unter Verwendung von unterschiedlichen zugrunde liegenden HTTP-Verbindungen werden zwei Nachrichten mit unterschiedlichen Präfixen gesendet. Legen Sie das Präfix durch Hinzufügen von Schlüssel/Wert-Paar an der Nachricht <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=fullName> Eigenschaft. Der Schlüssel ist "HttpTransportConnectionGroupNamePrefix"; der Wert ist das gewünschte Präfix.  
  
        -   **Verwenden verschiedene kanalfactorys**  
  
             Benutzer können zudem ein Feature aktivieren, das sicherstellt, dass die mithilfe von anhand unterschiedlicher Kanalfaktoren erstellten Kanälen gesendeten Nachrichten unterschiedliche zugrunde liegende HTTP-Verbindungen verwenden. Zum Aktivieren dieses Features müssen die Benutzer die folgende `appSetting` auf `true` festlegen:  
  
            ```  
  
            <appSettings>  
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />  
            </appSettings>  
  
            ```  
  
-   **Windows Workflow Foundation (WWF)**  
  
     Sie können nun die Anzahl der Sekunden angeben, die ein Workflowdienst an einer gestörten Vorgangsanforderung festhält, wenn ein ausstehendes Nicht-Protokoll-Lesezeichen vorliegt, bevor für die Anforderung ein Timeout ausgelöst wird. Ein Nicht-Protokoll-Lesezeichen ist ein Lesezeichen, das nicht mit ausstehenden Receive-Aktivitäten verknüpft ist. Bei einigen Aktivitäten werden Nicht-Protokoll-Lesezeichen in ihrer Implementierung erstellt. Es ist daher ggf. nicht offensichtlich, ob ein Nicht-Protokoll-Lesezeichen vorhanden ist. Dazu zählen der Status und die Auswahl. Wenn Sie über einen Workflowdienst verfügen, der mit einem Statuscomputer implementiert wurde oder eine Auswahlaktivität enthält, verfügen Sie sehr wahrscheinlich über Nicht-Protokoll-Lesezeichen. Sie geben das Intervall an, indem Sie eine Zeile wie die folgende zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen:  
  
    ```  
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>  
    ```  
  
     Der Standardwert beträgt 60 Sekunden. Wenn `value` auf „0“ festgelegt ist, werden gestörte Anforderungen sofort mit einem Fehlertext abgelehnt, der wie folgt aussieht:  
  
    ```Output  
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.   
    ```  
  
     Hierbei handelt es sich um dieselbe Meldung, die Sie empfangen, wenn Sie eine Meldung in Bezug auf einen gestörten Vorgang empfangen und keine Nicht-Protokoll-Lesezeichen vorliegen.  
  
     Wenn der Wert des `FilterResumeTimeoutInSeconds`-Elements nicht null entspricht, liegen keine Nicht-Protokoll-Lesezeichen vor, und das Timeoutintervall läuft ab, wobei beim Vorgang Fehler auftreten und eine Timeoutmeldung angezeigt wird.  
  
-   **Transaktionen**  
  
     Sie können jetzt den verteilten Transaktions-ID enthalten, für die Transaktion, die eine Ausnahme verursacht hat abgeleitet <xref:System.Transactions.TransactionException> ausgelöst wird. Hierzu müssen Sie den folgenden Schlüssel zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen.  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     Der Standardwert ist `false`.  
  
-   **Netzwerk**  
  
    -   **Socket-Wiederverwendung**  
  
         Windows 10 umfasst einen neuen hochskalierbaren Netzwerkalgorithmus, der eine bessere Verwendung von Computerressourcen ermöglicht, indem lokale Ports für ausgehende TCP-Verbindungen verwendet werden. .NET Framework 4.6 unterstützt den neuen Algorithmus, wodurch .NET-Apps von diesem neuen Verhalten profitieren können. In früheren Windows-Versionen gab es einen Grenzwert für gleichzeitige, künstliche Verbindungen (für gewöhnlich 16.384, die Standardgröße des dynamischen Portbereichs), wodurch die Skalierbarkeit eines Diensts begrenzt werden konnte, indem unter Lastbedingungen eine Portauslastung verursacht werden konnte.  
  
         In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] wurden zwei neue APIs hinzugefügt, um die Portwiederverwendung zu aktivieren, wodurch die 64K-Begrenzung für gleichzeitige Verbindungen effektiv entfernt wurde:  
  
        -   Die <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> -Enumerationswert.  
  
        -   Die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> Eigenschaft.  
  
         In der Standardeinstellung die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> Eigenschaft ist `false` , wenn die `HWRPortReuseOnSocketBind` Wert der `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` Registrierungsschlüssel auf 0 x 1 festgelegt ist. Legen Sie zum Aktivieren der Wiederverwendung von lokalen Port für HTTP-Verbindungen die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> -Eigenschaft `true`. Dies bewirkt, dass alle ausgehenden TCP-Socket-Verbindung von <xref:System.Net.Http.HttpClient> und <xref:System.Net.HttpWebRequest> mit einer neuen Windows 10-Socketoption [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), mit der lokale Port Wiederverwendung.  
  
         Entwickler, die eine Anwendung mit Sockets können angeben, die <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> option, wenn eine Methode aufrufen, wie z. B. <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=fullName> , damit ausgehende Sockets lokale Ports während der Bindung wiederverwenden.  
  
    -   **Unterstützung für internationale Domänennamen und PunyCode**  
  
         Eine neue Eigenschaft, <xref:System.Uri.IdnHost%2A>, hinzugefügt wurde der <xref:System.Uri> Klasse, um die internationale Domänennamen und PunyCode besser zu unterstützen.  
  
-   **Ändern der Größe von Windows Forms-Steuerelementen.**  
  
     Dieses Feature wurde erweitert, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] enthalten die <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.ToolStripSplitButton> Typen und die durch angegebene Rechteck der <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> Eigenschaft beim Zeichnen verwendet eine <xref:System.Drawing.Design.UITypeEditor>.  
  
     Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **Unterstützung für codepagecodierungen**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)] unterstützt primär Unicode-Codierungen und bietet standardmäßig eingeschränkte Unterstützung für Codepagecodierungen. Sie können Unterstützung für codeseitencodierungen, die in .NET Framework, jedoch nicht unterstützt in verfügbaren hinzufügen [!INCLUDE[net_core](../../../includes/net-core-md.md)] von codeseitencodierungen mit der <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=fullName> Methode. Weitere Informationen finden Sie unter [System.Text.CodePagesEncodingProvider](https://msdn.microsoft.com/en-us/library/system.text.codepagesencodingprovider.aspx).  
  
-   **.NET native**  
  
     Windows-Apps für Windows 10, die auf [!INCLUDE[net_core](../../../includes/net-core-md.md)] ausgerichtet und in C# oder Visual Basic geschrieben sind, können eine neue Technologie nutzen, die Apps in systemeigenen Code kompiliert statt in IL. Sie erzeugen Apps, die sich durch kürzere Start- und Ausführungszeiten auszeichnen. Weitere Informationen finden Sie unter [Kompilieren von Apps mit .NET Native](../../../docs/framework/net-native/index.md). Eine Übersicht über .NET-Native, der untersucht werden, wie es sowohl von JIT-Kompilierung als auch von NGEN unterscheidet und was dies bedeutet, dass für Ihren Code finden Sie unter [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md).  
  
     Ihre Apps werden beim Kompilieren mit Visual Studio 2015 standardmäßig in systemeigenen Code kompiliert. Weitere Informationen finden Sie unter [erste Schritte mit .NET Native](../../../docs/framework/net-native/getting-started-with-net-native.md).  
  
     Um das Debuggen von .NET Native-Apps zu unterstützen, wurden der API für nicht verwaltetes Debugging eine Reihe neuer Schnittstellen und Enumerationen hinzugefügt. Weitere Informationen finden Sie unter der [Debuggen (Referenz zur nicht verwalteten API)](../../../ml/index.xml) Thema.  
  
-   **Open-Source-Pakete von .NET Framework**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)]Pakete wie die unveränderlichen Auflistungen, [SIMD-APIs](http://go.microsoft.com/fwlink/?LinkID=518639), und wie die Netzwerk-APIs finden Sie in der <xref:System.Net.Http> Namespace stehen jetzt als open Source-Pakete auf [GitHub](https://github.com/). Um Zugriff auf den Code finden Sie unter [NetFx auf GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Weitere Informationen und wie Sie zu diesen Paketen beitragen können, finden Sie unter [.NET Core und Open-Source-](../../../docs/framework/get-started/net-core-and-open-source.md), [.NET-Startseite auf GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>Neuigkeiten in .NET Framework 4.5.2  
  
-   **Neue APIs für ASP.NET-Anwendungen.** Die neue <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=fullName> und <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=fullName> Methoden können Sie überprüfen und ändern Antwortheader und Statuscodes, wie die Antwort an die Clientanwendung übergeben. Sie sollten diese Methoden anstelle von der <xref:System.Web.HttpApplication.PreSendRequestHeaders> und <xref:System.Web.HttpApplication.PreSendRequestContent> Ereignisse effizienter und zuverlässiger werden.  
  
     Die <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=fullName> Methode können Sie die Ausführung kleiner Hintergrund-Arbeitsaufgaben planen. ASP.NET überwacht diese Aufgaben und verhindert, dass IIS den Arbeitsprozess abrupt beendet, bevor alle Hintergrund-Arbeitsaufgaben abgeschlossen wurden. Diese Methode kann nicht außerhalb von verwalteten ASP.NET-App-Domänen aufgerufen werden.  
  
     Die neue <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=fullName> und <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=fullName> Eigenschaften zurückzugeben, boolesche Werte, die angeben, ob die Antwortheader geschrieben wurden. Sie können sicherstellen, diese Eigenschaften verwenden, die Aufrufe von APIs wie z. B. <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=fullName> (die Ausnahmen auslösen, wenn der Header geschrieben wurden) erfolgreich ausgeführt werden.  
  
-   **Ändern der Größe von Windows Forms-Steuerelementen.** Dieses Feature wurde erweitert. Sie können nun die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten der folgenden zusätzlichen Steuerelemente anzupassen (z. B. der Dropdownpfeil in Combofeldern):  
  
     <xref:System.Windows.Forms.ComboBox>   
     <xref:System.Windows.Forms.ToolStripComboBox>   
     <xref:System.Windows.Forms.ToolStripMenuItem>   
     <xref:System.Windows.Forms.Cursor>   
     <xref:System.Windows.Forms.DataGridView>   
     <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
     Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **Neues Workflow-Feature.** Ein Ressourcen-Manager, ist die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> Methode (und daher Implementieren der <xref:System.Transactions.IPromotableSinglePhaseNotification> Schnittstelle) können Sie die neue <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> Methode, um Folgendes abzufragen:  
  
    -   Stufen Sie die Transaktion zu einer Microsoft Distributed Transaction Coordinator (MSDTC)-Transaktion herauf.  
  
    -   Ersetzen Sie <xref:System.Transactions.IPromotableSinglePhaseNotification> mit einem <xref:System.Transactions.ISinglePhaseNotification>, eine dauerhafte Eintragung, die einphasige Commits unterstützt.  
  
     Dies kann innerhalb derselben App-Domäne erfolgen, und erfordert keinen zusätzlichen nicht verwalteten Code für die Interaktion mit MSDTC für die Höherstufung. Die neue Methode kann aufgerufen werden, nur, wenn ein ausstehender Aufruf von <xref:System.Transactions?displayProperty=fullName> an der <xref:System.Transactions.IPromotableSinglePhaseNotification> `Promote` -Methode, die von der heraufstufbaren Eintragung implementiert wird.  
  
-   **Profilerstellungsverbesserungen.** Die folgenden neuen, nicht verwalteten Profilerstellungs-APIs bieten eine robustere Profilerstellung:  
  
     [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](../../../ocs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)   
     [COR_PRF_HIGH_MONITOR-Enumeration](../../../ocs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)   
     [GetAssemblyReferences-Methode](../Topic/ICorProfilerCallback6::GetAssemblyReferences%20Method.md)   
     [GetEventMask2-Methode](../Topic/ICorProfilerInfo5::GetEventMask2%20Method.md)   
     [SetEventMask2-Methode](../Topic/ICorProfilerInfo5::SetEventMask2%20Method.md)   
     [AddAssemblyReference-Methode](../Topic/ICorProfilerAssemblyReferenceProvider::AddAssemblyReference%20Method.md)  
  
     Frühere `ICorProfiler`-Implementierungen unterstützten Lazy Loading für abhängige Assemblys. Die neue Profilerstellungs-API benötigt abhängige Assemblys, die vom Profiler zum sofortigen Laden eingefügt werden, anstatt nach der vollständigen Initialisierung der App geladen zu werden. Diese Änderung betrifft keine Benutzer der existierenden `ICorProfiler`-APIs.  
  
-   **Verbesserungen beim Debugging.** Die folgenden neuen, nicht verwalteten Debugging-APIs bieten bessere Profilerintegration. Beim Debuggen von Abbildern haben Sie nun Zugriff auf die vom Profiler eingefügten Metadaten sowie auf lokale Variablen und den von ReJIT-Anfragen des Compilers eingefügten Code.  
  
     [SetWriteableMetadataUpdateMode-Methode](../Topic/ICorDebugProcess7::SetWriteableMetadataUpdateMode%20Method.md)   
     [EnumerateLocalVariablesEx-Methode](../Topic/ICorDebugILFrame4::EnumerateLocalVariablesEx%20Method.md)   
     [GetLocalVariableEx-Methode](../Topic/ICorDebugILFrame4::GetLocalVariableEx%20Method.md)   
     [GetCodeEx-Methode](../Topic/ICorDebugILFrame4::GetCodeEx%20Method.md)   
     [GetActiveReJitRequestILCode-Methode](../Topic/ICorDebugFunction3::GetActiveReJitRequestILCode%20Method.md)   
     [GetInstrumentedILMap-Methode](../Topic/ICorDebugILCode2::GetInstrumentedILMap%20Method.md)  
  
-   **Änderungen an der ereignisablaufverfolgung.** .NET Framework 4.5.2 unterstützt prozessexterne Ereignisablaufverfolgung für Windows (ETW)-basierte Aktivitätsverfolgung für eine größere Oberfläche. Auf diese Weise können Advanced Power Management (APM)-Hersteller einfache Tools zur Messung der Kosten einzelner threadübergreifender Anfragen und Aktivitäten anbieten.  Diese Ereignisse werden nur ausgelöst, wenn sie von einem ETW-Controller aktiviert wurden. Die Änderungen betreffen daher keinen zuvor geschriebenen ETW-Code oder Code, der mit deaktivierter ETW ausgeführt wird.  
  
-   **Heraufstufen einer Transaktions und deren Konvertierung in eine dauerhafte Eintragung**  
  
     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> wird eine neue API hinzugefügt zu .NET Framework 4.5.2 und 4.6:  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     Die Methode kann verwendet werden, durch eine Eintragung, die zuvor von erstellt wurde <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> als Antwort auf die <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> Methode. Sie fragt `System.Transactions` ab, um die Transaktion zu einer MSDTC-Transaktion heraufzustufen und um die heraufstufbare Eintragung zu einer dauerhaften Eintragung zu „konvertieren“. Nach dem erfolgreichen dieser Methode Abschluss die <xref:System.Transactions.IPromotableSinglePhaseNotification> Schnittstelle wird nicht mehr verwiesen werden, indem `System.Transactions`, und zukünftige Benachrichtigungen für die bereitgestellte kommen <xref:System.Transactions.ISinglePhaseNotification> Schnittstelle. Die entsprechende Eintrag muss als eine dauerhafte Eintragung fungieren und die Transaktionsprotokollierung und -wiederherstellung unterstützen. Finden Sie unter <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName> Details. Darüber hinaus muss die Eintragung unterstützen <xref:System.Transactions.ISinglePhaseNotification>.  Diese Methode kann *nur* aufgerufen werden, während der Verarbeitung einer <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> aufrufen. Wenn dies nicht der Fall ist ein <xref:System.Transactions.TransactionException> Ausnahme ausgelöst.  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>Neuigkeiten in .NET Framework 4.5.1  
 **Updates für April 2014**:  
  
-   [Visual Studio 2013 Update 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) enthält Updates für die Portable Class Library-Vorlagen für diese Szenarien zu unterstützen:  
  
    -   Sie können die Windows-Runtime APIs in portablen Bibliotheken einsetzen, die Windows 8.1, Windows Phone 8.1 und Windows Phone Silverlight 8.1 als Ziel verwenden.  
  
    -   Sie können XAML (Windows.UI.XAML-Typen) in portablen Bibliotheken einsetzen, wenn Sie Windows 8.1 oder Windows Phone 8.1 als Ziel verwenden. Die folgenden XAML-Vorlagen werden unterstützt: Leere Seite, Ressourcenverzeichnis, Steuerelement mit Vorlagen und Benutzersteuerelement.  
  
    -   Sie können eine portable Komponente für Windows-Runtime (.winmd-Datei) für den Einsatz in Store-Apps erstellen, die Windows 8.1 und Windows Phone 8.1 als Ziel verwenden.  
  
    -   Sie können eine Windows Store- oder Windows Phone Store-Klassenbibliothek wie eine portable Klassenbibliothek neu zuweisen.  
  
     Weitere Informationen zu diesen Änderungen finden Sie unter [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
-   Der .NET Framework-Inhaltssatz enthält nun Dokumentation für [!INCLUDE[net_native](../../../includes/net-native-md.md)], eine Vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-Apps. [!INCLUDE[net_native](../../../includes/net-native-md.md)] kompiliert Ihre Apps direkt in systemeigenen Code anstelle einer Intermediate Language (IL) und erzielt dadurch eine bessere Leistung. Weitere Informationen finden Sie unter [Kompilieren von Apps mit .NET Native](../../../docs/framework/net-native/index.md).  
  
-   Die [.NET Framework Reference Source](http://referencesource.microsoft.com/) bietet ein neues browsing-Erlebnis und erweiterte Funktionen. Sie können jetzt den .NET Framework-Quellcode online Durchsuchen [Referenz herunterladen](http://referencesource.microsoft.com/download.html) zur Offlineanzeige oder schrittweise zu durchlaufen (inklusive Patches und Updates) während des Debuggens. Weitere Informationen finden Sie im Blogeintrag [ein neues Aussehen for .NET Reference Source](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx).  
  
 .NET Framework 4.5.1 enthält die folgenden neuen Kernfunktionen und -optimierungen:  
  
-   Automatische Bindungsumleitung für Assemblys. Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] können beim Kompilieren einer App, deren Ziel [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] ist, Bindungsumleitungen zur App-Konfigurationsdatei hinzugefügt werden, wenn die App oder ihre Komponenten sich auf mehrere Versionen derselben Assembly beziehen. Sie können diese Funktion auch für Projekte aktivieren, die frühere Versionen von .NET Framework als Ziel haben. Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).  
  
-   Fähigkeit, Diagnoseninformationen zu erfassen, um Entwicklern zu helfen, die Leistung von Server- und Cloud-Anwendungen zu verbessern. Weitere Informationen finden Sie unter der <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> und <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> Methoden in der <xref:System.Diagnostics.Tracing.EventSource> Klasse.  
  
-   Fähigkeit, während einer Garbage Collection den großen Objektheap (Large Object Heap, LOH) explizit zu komprimieren. Weitere Informationen finden Sie unter der <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName> Eigenschaft.  
  
-   Zusätzliche Leistungsverbesserungen wie ASP.NET-App-Unterbrechung, Multikern-JIT-Verbesserungen und schnellere App-Starts nach einem .NET Framework-Update. Weitere Informationen finden Sie unter der [.NET Framework 4.5.1-Ankündigung](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) und [ASP.NET-App suspend](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx) Blogbeitrag.  
  
 Verbesserungen für Windows Forms-Anwendungen:  
  
-   Größenänderungen in Windows Forms-Steuerelementen. Sie können die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten von Steuerelementen anzupassen (z. B. die Symbole in einem Eigenschaftenraster), indem Sie diese Funktion über einen Eintrag in der Anwendungskonfigurationsdatei (app.config) für Ihre App aktivieren. Dieses Feature wird zurzeit für die folgenden Windows Forms-Steuerelemente unterstützt:  
  
     <xref:System.Windows.Forms.PropertyGrid>   
     <xref:System.Windows.Forms.TreeView>   
     Einige Aspekte der <xref:System.Windows.Forms.DataGridView> (siehe [neue Features in 4.5.2](#v452) für Weitere unterstützte Steuerelemente)  
  
     Um dieses Feature zu aktivieren, fügen Sie einen neuen <> \> Element auf die Konfigurationsdatei (app.config) und legen die `EnableWindowsFormsHighDpiAutoResizing` Element `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 Zu Verbesserungen beim Debuggen Ihrer .NET Framework-Apps in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] zählen:  
  
-   Rückgabewerte im Visual Studio-Debugger. Wenn Sie eine verwaltete App in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] debuggen, werden Rückgabetypen und -werte für Methoden im Fenster "Auto" angezeigt. Diese Informationen sind für Desktop-, Windows Store- und Windows Phone-Apps verfügbar. Weitere Informationen finden Sie unter [Überprüfen von Rückgabewerten der Methodenaufrufe](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) in der MSDN Library.  
  
-   "Bearbeiten und Fortfahren" für 64-Bit-Apps. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] unterstützt die Funktion "Bearbeiten und Fortfahren" für verwaltete 64-Bit-Apps für Desktops, Windows Store und Windows Phone. Die vorhandenen Einschränkungen bleiben für 32-Bit- und 64-Bit-apps wirksam (finden Sie im letzten Abschnitt der [unterstützte Codeänderungen (c#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx) Artikel).  
  
-   Async-bewusstes Debuggen. Um das Debuggen asynchroner Apps in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] zu vereinfachen, wird der Infrastrukturcode, der von Compilern zur Unterstützung asynchronen Programmierens bereitgestellt wird, in der Aufrufliste ausgeblendet. Ebenfalls erfolgt dort eine Verkettung mit logisch übergeordneten Rahmen, sodass der logischen Programmausführung übersichtlicher gefolgt werden kann. Ein Aufgabenfenster ersetzt das Fenster "Parallele Aufgaben" und zeigt Aufgaben an, die sich auf einen bestimmten Haltepunkt beziehen. Außerdem werden alle anderen Aufgaben angezeigt, die momentan aktiv oder in der App geplant sind. Informieren Sie sich über dieses Feature im Abschnitt "Async-aware debugging", der die [.NET Framework 4.5.1-Ankündigung](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
-   Bessere Ausnahmeunterstützung für Windows-Runtime-Komponenten. In [!INCLUDE[win81](../../../includes/win81-md.md)] behalten Ausnahmen, die sich aus Windows Store-Apps ergeben, Informationen zum Fehler, der die Ausnahme ausgelöst hat, sogar über Sprachgrenzen bei. Informieren Sie sich über dieses Feature im Abschnitt "Windows Store-app-Entwicklung", der die [.NET Framework 4.5.1-Ankündigung](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
 Beginnend mit [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], können Sie die [Managed Profile Guided Optimization Tool (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) zur Optimierung [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps sowie desktop-apps.  
  
 Informationen zu neuen Funktionen in ASP.NET 4.5.1 finden Sie unter [ASP.NET 4.5.1 und Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) auf der ASP.NET-Website.  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>Neuigkeiten in .NET Framework 4.5  
  
### <a name="core-new-features-and-improvements"></a>Wichtige neue Features und Verbesserungen  
  
-   Weniger Systemneustarts durch Erkennen und Schließen von .NET Framework 4-Anwendungen bei der Bereitstellung. Finden Sie unter [Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen](../../../docs/framework/deployment/reducing-system-restarts.md).  
  
-   Unterstützung von mehr als 2 Gigabyte (GB) großen Arrays auf 64-Bit-Plattformen. Sie können die Funktion in der Anwendungskonfiguration aktivieren. Finden Sie unter der [ <> \> Element](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), das auch andere Einschränkungen zur Objekt- und Arraygröße auflistet.  
  
-   Bessere Leistung durch Garbage Collection im Hintergrund für Server. Wenn Sie die Garbage Collection auf dem Server in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] verwenden, wird die Garbage Collection im Hintergrund automatisch aktiviert. Finden Sie im Abschnitt Server Garbage Collection im Hintergrund den [Grundlagen der Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md) Thema.  
  
-   Just-In-Time (JIT)-Kompilierung im Hintergrund zur Verbesserung der Anwendungsleistung, die optional auf Mehrkernprozessoren verfügbar ist. Finden Sie unter <xref:System.Runtime.ProfileOptimization>.  
  
-   Festlegen der Zeit, die das Modul für reguläre Ausdrücke zum Auflösen eines regulären Ausdrucks bis zum Timeout benötigen darf. Finden Sie unter der <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=fullName> Eigenschaft.  
  
-   Definieren der Standardkultur für eine Anwendungsdomäne. Finden Sie unter der <xref:System.Globalization.CultureInfo> Klasse.  
  
-   Konsolenunterstützung für Unicode-Codierung (UTF-16). Finden Sie unter der <xref:System.Console> Klasse.  
  
-   Unterstützung für die Versionierung kulturabhängiger Zeichenfolgenreihenfolgen und -vergleichsdaten. Finden Sie unter der <xref:System.Globalization.SortVersion> Klasse.  
  
-   Bessere Leistung beim Abrufen von Ressourcen. Finden Sie unter [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  
  
-   Verbesserte ZIP-Komprimierung zur Reduzierung der Größe einer komprimierten Datei. Finden Sie unter der <xref:System.IO.Compression?displayProperty=fullName> Namespace.  
  
-   Möglichkeit zum Anpassen von Reflektionskontext zum Überschreiben von Standardverhalten der Reflektion über die <xref:System.Reflection.Context.CustomReflectionContext> Klasse.  
  
-   Unterstützung für die Version des Internationalized Domain Names in Applications (IDNA) 2008 standard bei der <xref:System.Globalization.IdnMapping?displayProperty=fullName> Klasse dient auf [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
-   Delegieren des Zeichenfolgenvergleichs an das Betriebssystem, wobei Unicode 6.0 implementiert wird, wenn .NET Framework in [!INCLUDE[win8](../../../includes/win8-md.md)] verwendet wird. Bei Ausführung auf anderen Plattformen verwendet .NET Framework eigene Zeichenfolgenvergleichsdaten, wobei Unicode 5.x. implementiert wird. Finden Sie unter der <xref:System.String> -Klasse und im Abschnitt Hinweise der <xref:System.Globalization.SortVersion> Klasse.  
  
-   Berechnen der Hashcodes für Zeichenfolgen pro Anwendungsdomäne. See [<>\> Element](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).  
  
-   Geben Sie die Reflektion unterstützt eine Teilung zwischen <xref:System.Type> und <xref:System.Reflection.TypeInfo> Klassen. Finden Sie unter [Reflektion in .NET Framework für Windows Store-Apps](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md).  
  
### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bietet das Managed Extensibility Framework (MEF) folgende neue Funktionen:  
  
-   Unterstützung von generischen Typen.  
  
-   Konventionsbasiertes Programmiermodell zum Erstellen von Teilen auf Grundlage von Namenskonventionen anstelle von Attributen.  
  
-   Mehrere Bereiche.  
  
-   Eine Teilmenge von MEF, die Sie verwenden können, wenn Sie Apps im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] erstellen. Diese Teilmenge steht als ein [Downloadpaket](http://go.microsoft.com/fwlink/?LinkId=256238) aus dem NuGet-Katalog. Um das Paket zu installieren, öffnen Sie das Projekt in Visual Studio, wählen Sie **NuGet-Pakete verwalten** aus der **Projekt** Menü, und suchen Sie online nach dem `Microsoft.Composition` Paket.  
  
 Weitere Informationen finden Sie unter [Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md).  
  
### <a name="asynchronous-file-operations"></a>Asynchrone Dateivorgänge  
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurden neue asynchrone Funktionen zu den Programmiersprachen C# und Visual Basic hinzugefügt. Diese Funktionen ergänzen ein aufgabenbasiertes Modell zum Ausführen von asynchronen Vorgängen. Verwenden Sie dieses neue Modell mithilfe der asynchronen Methoden in den E/A-Klassen. Finden Sie unter [asynchrone Datei-e/a](../../../docs/standard/io/asynchrone-datei-e-a.md).  
  
<a name="tools"></a>   
### <a name="tools"></a>Tools  
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] können Sie mit dem Resource File Generator-Tool (Resgen.exe) aus einer RESOURCES-Datei, die in einer .NET Framework-Assembly eingebettet ist, eine RESW-Datei für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps erstellen. Weitere Informationen finden Sie unter [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).  
  
 Mit Managed Profile Guided Optimization (Mpgo.exe) können Sie die Anwendungsstartzeit, die Arbeitsspeicherauslastung (Workingsetgröße) und den Durchsatz verbessern, indem Sie die Assemblys systemeigener Abbilder optimieren. Das Befehlszeilentool generiert Profildaten für Anwendungsassemblys systemeigener Abbilder. Finden Sie unter [Mpgo.exe (verwaltetes, Profilgesteuertes Optimierungstool)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md). Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] können Sie Mpgo.exe verwenden, um [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps und Desktop-Apps zu optimieren.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>Parallele Computervorgänge  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] stellt mehrere neue Funktionen und Verbesserungen für parallele Berechnung bereit. Dazu gehören leistungsfähigere, erweiterte Steuerungsmöglichkeiten, verbesserte Unterstützung für asynchrone Programmierung, eine neue Datenflussbibliothek und verbesserte Unterstützung für paralleles Debuggen und Leistungsanalyse. Siehe den Eintrag [What's New for Parallelism in .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) in der parallelen Programmierung mit .NET Blog.  
  
<a name="web"></a>   
### <a name="web"></a>Web  
 In ASP.NET 4.5 und 4.5.1 wurden die Modellbindung für Webformulare, WebSocket-Unterstützung, asynchrone Handler, Leistungserweiterungen und viele weitere Funktionen hinzugefügt. Weitere Informationen finden Sie in den folgenden Ressourcen:  
  
-   [ASP.NET 4.5 und Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) in der MSDN Library.  
  
-   [ASP.NET 4.5.1 und Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) auf der ASP.NET-Website.  
  
<a name="networking"></a>   
### <a name="networking"></a>Netzwerk  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] stellt eine neue Programmierschnittstelle für HTTP-Anwendungen bereit. Weitere Informationen finden Sie im neuen <xref:System.Net.Http?displayProperty=fullName> und <xref:System.Net.Http.Headers?displayProperty=fullName> Namespaces.  
  
 Support steht auch eine neue Programmierschnittstelle für anzunehmen und interagieren mit einem WebSocket-Verbindung mithilfe der vorhandenen <xref:System.Net.HttpListener> und verwandte Klassen. Weitere Informationen finden Sie im neuen <xref:System.Net.WebSockets> Namespace und die <xref:System.Net.HttpListener> Klasse.  
  
 Darüber hinaus enthält [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] folgende Netzwerkfunktionsverbesserungen:  
  
-   RFC-kompatible URI-Unterstützung. Weitere Informationen finden Sie unter <xref:System.Uri> und verwandte Klassen.  
  
-   Unterstützung für IDN (Internationalized Domain Name)-Analysen. Weitere Informationen finden Sie unter <xref:System.Uri> und verwandte Klassen.  
  
-   Unterstützung für E-Mail-Adressen-Internationalisierung (EAI). Weitere Informationen finden Sie unter der <xref:System.Net.Mail> Namespace.  
  
-   Verbesserte IPv6-Unterstützung. Weitere Informationen finden Sie unter der <xref:System.Net.NetworkInformation> Namespace.  
  
-   Dual-Modus-Socket-Unterstützung. Weitere Informationen finden Sie unter der <xref:System.Net.Sockets.Socket> und <xref:System.Net.Sockets.TcpListener> Klassen.  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 In der Version [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurde Windows Presentation Foundation (WPF) in vielen Bereichen überarbeitet und verbessert. Dazu gehören:  
  
-   Die neue <xref:System.Windows.Controls.Ribbon.Ribbon> -Steuerelement, das können Sie eine Menüband-Benutzeroberfläche zu implementieren, die eine Symbolleiste für den Schnellzugriff, ein Anwendungsmenü und Registerkarten hostet.  
  
-   Die neue <xref:System.ComponentModel.INotifyDataErrorInfo> -Schnittstelle, die synchrone und asynchrone datenvalidierung unterstützt.  
  
-   Neue Funktionen für die <xref:System.Windows.Controls.VirtualizingPanel> und <xref:System.Windows.Threading.Dispatcher> Klassen.  
  
-   Verbesserte Leistung beim Anzeigen großer Datengruppierungen sowie durch den Zugriff auf Auflistungen in Nicht-UI-Threads.  
  
-   Binden von Daten an statische Eigenschaften, Datenbindung an benutzerdefinierte Typen implementiert die <xref:System.Reflection.ICustomTypeProvider> -Schnittstelle und das Abrufen von Datenbindungsinformationen von einem Bindungsausdruck.  
  
-   Neupositionierung von Daten bei Wertänderung (Live-Strukturierung).  
  
-   Überprüfen einer möglicherweise getrennten Verbindung des Datenkontexts für einen Elementcontainer.  
  
-   Festlegen der Zeit, die zwischen Eigenschaftenänderungen und Datenquellenupdates verstreichen soll.  
  
-   Verbesserte Unterstützung für das Implementieren schwacher Ereignismuster. Zudem können Ereignisse jetzt Markuperweiterungen akzeptieren.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 Um das Schreiben und Verwalten von Windows Communication Foundation (WCF)-Anwendungen zu erleichtern, wurden in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] folgende Funktionen hinzugefügt:  
  
-   Vereinfachung von generierten Konfigurationsdateien.  
  
-   Unterstützung für Contract-First-Entwicklung.  
  
-   Leichteres Konfigurieren des ASP.NET-Kompatibilitätsmodus.  
  
-   Änderungen in den standardmäßigen Transporteigenschaftswerten, um die Wahrscheinlichkeit zu reduzieren, dass Sie sie festlegen müssen.  
  
-   Aktualisiert die <xref:System.Xml.XmlDictionaryReaderQuotas> Klasse, um die Wahrscheinlichkeit zu verringern, die Sie Kontingente für XML-Wörterbuch-Reader manuell konfigurieren.  
  
-   Validierung von WCF-Konfigurationsdateien von Visual Studio als Teil des Buildprozesses, sodass Sie Konfigurationsfehler erkennen können, bevor Sie die Anwendung ausführen.  
  
-   Neue Unterstützung für asynchrones Streaming.  
  
-   Neue HTTPS-Protokollzuordnung zur leichteren Bereitstellung eines Endpunkts über HTTPS mit IIS (Internetinformationsdienste).  
  
-   Generieren von Metadaten in einem einzelnen WSDL-Dokument durch Anfügen von `?singleWSDL` an die Dienst-URL.  
  
-   Websockets-Unterstützung für echte bidirektionale Kommunikation über die Ports 80 und 443 mit TCP-transportähnlichen Leistungsmerkmalen.  
  
-   Unterstützung für das Konfigurieren von Diensten im Code.  
  
-   XML-Editor-QuickInfos.  
  
-   <xref:System.ServiceModel.ChannelFactory> Zwischenspeichern unterstützt.  
  
-   Unterstützung für die Komprimierung binärer Encoder.  
  
-   Unterstützung für einen UDP-Transport, mit dem Entwickler "Fire and Forget" (Auslösen und Vergessen)-Messaging-Dienste schreiben können. Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.  
  
-   Unterstützung mehrerer Authentifizierungsmodi auf einem einzelnen WCF-Endpunkt beim Verwenden von HTTP-Transport und -Transportsicherheit.  
  
-   Unterstützung für WCF-Dienste, die internationale Domänennamen (IDNs) verwenden.  
  
 Weitere Informationen finden Sie unter [Neuigkeiten in Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 In der Version [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] gibt es jetzt viele neue Funktionen in Windows Workflow Foundation (WF), darunter:  
  
-   Zustandsautomatworkflows, die als Teil von .NET Framework 4.0.1 eingeführt wurden ([.NET Framework 4 Platform Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)). Dieses Update umfasste mehrere neue Klassen und Aktivitäten, sodass Entwickler Zustandsautomatworkflows erstellen konnten. Diese Klassen und Aktivitäten wurden für [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] aktualisiert und umfassen nun Folgendes:  
  
    -   Festlegen von Haltepunkten für Zustände.  
  
    -   Kopieren und Einfügen von Übergängen im Workflow Designer.  
  
    -   Designerunterstützung für das Erstellen von freigegebenen Triggerübergängen.  
  
    -   Aktivitäten zum Erstellen von Zustandsautomatworkflows, einschließlich: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State>, und <xref:System.Activities.Statements.Transition>.  
  
-   Verbesserte Workflow Designer-Funktionen, z. B.:  
  
    -   Verbesserte workflowsuchfunktionen in Visual Studio, einschließlich **Schnellsuche** und **in Dateien suchen**.  
  
    -   Automatisches Erstellen einer Sequenzaktivität, wenn eine zweite untergeordnete Aktivität zu einer Containeraktivität hinzugefügt wird, und Einschließen beider Aktivitäten in die Sequenzaktivität.  
  
    -   Schwenk-Unterstützung zur Änderung des sichtbaren Teils eines Workflows ohne die Verwendung von Bildlaufleisten.  
  
    -   Ein neues **Dokumentgliederung** Ansicht, zeigt die Komponenten eines Workflows in einer strukturähnlichen Gliederungsansicht und können Sie, wählen Sie eine Komponente in der **Dokumentgliederung** anzeigen.  
  
    -   Hinzufügen von Anmerkungen zu Aktivitäten.  
  
    -   Definieren und Verarbeiten von Aktivitätsdelegaten mit dem Workflow Designer.  
  
    -   Automatisches Verbinden und Einfügen für Aktivitäten und Übergänge in Zustandsautomaten- und Flussdiagrammworkflows.  
  
-   Speichern der Ansichtszustandsinformationen für einen Workflow in einem einzelnen Element in der XAML-Datei, sodass Sie die Ansichtszustandsinformationen leicht finden und bearbeiten können.  
  
-   Eine NoPersistScope-Containeraktivität, damit untergeordnete Aktivitäten nicht beibehalten werden.  
  
-   Unterstützung von C#-Ausdrücken:  
  
    -   Visual Basic-Workflowprojekte verwenden Visual Basic-Ausdrücke, und C#-Workflowprojekte verwenden C#-Ausdrücke.  
  
    -   C#-Workflowprojekte, die in Visual Studio 2010 erstellt wurden und Visual Basic-Ausdrücke verwenden, sind mit C#-Workflowprojekten, die C#-Ausdrücke verwenden, kompatibel.  
  
-   Versionsverwaltungserweiterungen:  
  
    -   Die neue <xref:System.Activities.WorkflowIdentity> -Klasse, die eine Zuordnung zwischen einer beibehaltenen Workflowinstanz und ihrer Workflowdefinition bietet.  
  
    -   Seite-an-Seite-Ausführung mehrerer workflowversionen im selben Host, einschließlich <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
    -   Die Änderbarkeit der Definition einer beibehaltenen Workflowinstanz im Rahmen eines dynamischen Updates.  
  
-   Contract-First-Workflowdienstentwicklung, die das automatische Generieren von Aktivitäten zur Übereinstimmung mit einem vorhandenen Dienstvertrag unterstützt.  
  
 Weitere Informationen finden Sie unter [Neuigkeiten in Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).  
  
<a name="tailored"></a>   
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]  
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps werden für bestimmte Formularfaktoren entworfen und nutzen die Leistungsfähigkeit des Windows-Betriebssystems. Eine Teilmenge von [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder 4.5.1 kann mithilfe von C# oder Visual Basic zum Erstellen von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps in Windows verwendet werden. Diese Teilmenge wird aufgerufen, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] und wird einer [Übersicht über die](http://go.microsoft.com/fwlink/?LinkId=228491) im Windows Developer Center.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>Portable Klassenbibliotheken  
 Mit dem Projekt "Portable Klassenbibliothek" in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (und Folgeversionen) können Sie verwaltete Assemblys, die auf mehreren .NET Framework-Plattformen ausgeführt werden können, schreiben und erstellen. Mit einem "Portable Klassenbibliothek"-Projekt wählen Sie die Zielplattformen (wie Windows Phone und [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Die verfügbaren Typen und Member im Projekt werden automatisch auf die allgemeinen Typen und Member dieser Plattformen beschränkt. Weitere Informationen finden Sie unter [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
## <a name="see-also"></a>Siehe auch  
 [.NET Framework und Out-of-Band-Versionen](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [What's New in Visual Studio 2013](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 und Webtools für Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET und Visual Studio für Web](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Was ist neu in Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Was ist neu in Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [Was ist neu in Visual C++](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx)