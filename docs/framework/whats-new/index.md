---
title: Neues in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
ms.openlocfilehash: c651f5c02bd49acc593c585395bc52e9ee64f870
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714496"
---
# <a name="whats-new-in-the-net-framework"></a>Neues in .NET Framework

Dieser Artikel beschreibt wichtige Funktionen und Änderungen in den folgenden Versionen von .NET Framework:

- [.NET Framework 4.8](#v48)
- [.NET Framework 4.7.2](#v472)
- [.NET Framework 4.7.1](#v471)
- [.NET Framework 4.7](#v47)
- [.NET Framework 4.6.2](#v462)
- [.NET Framework 4.6.1](#v461)
- [.NET 2015 und .NET Framework 4.6](#v46)
- [.NET Framework 4.5.2](#v452)
- [.NET Framework 4.5.1](#v451)
- [.NET Framework 4.5](#v45)

Dieser Artikel enthält keine umfassenden Informationen zu jeder neuen Funktion und unterliegt möglichen Änderungen. Allgemeine Informationen zu .NET Framework finden Sie unter [Erste Schritte](../get-started/index.md). Informationen zu unterstützten Plattformen finden Sie unter [Systemanforderungen](../get-started/system-requirements.md). Downloadlinks und Installationsanweisungen finden Sie im [Installationshandbuch](../install/guide-for-developers.md).

> [!NOTE]
> Das .NET Framework-Team veröffentlicht zusätzlich mit NuGet Funktionen außer der Reihe, um die Plattformunterstützung zu erweitern und neue Funktionen einzuführen, z. B. unveränderliche Auflistungen und SIMD-fähige Vektortypen. Weitere Informationen finden Sie unter [Zusätzliche Klassenbibliotheken und APIs](../additional-apis/index.md) und [.NET Framework und Out-of-Band-Releases](../get-started/the-net-framework-and-out-of-band-releases.md).
> Siehe die [vollständige Liste der NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) für .NET Framework.

<a name="v48" />

## <a name="introducing-net-framework-48"></a>Vorstellung von .NET Framework 4.8

.NET Framework 4.8 baut auf früheren Versionen von .NET Framework 4.x auf und umfasst zahlreiche Fehlerkorrekturen und neue Features in einem gewohnt stabilen Produkt.

### <a name="downloading-and-installing-net-framework-48"></a>Herunterladen und Installieren von .NET Framework 4.8

Sie können .NET Framework 4.8 an folgenden Stellen herunterladen:

- [Webinstaller für .NET Framework 4.8](https://go.microsoft.com/fwlink/?LinkId=2085155)

- [Offlineinstaller für .NET Framework 4.8](https://go.microsoft.com/fwlink/?linkid=2088631)

.NET Framework 4.8 kann unter Windows 10, Windows 8.1, Windows 7 SP1 und den entsprechenden Serverplattformen (beginnend mit Windows Server 2008 R2 SP1) installiert werden. Sie können .NET Framework 4.8 wahlweise mit dem Webinstaller oder Offlineinstaller installieren. Die empfohlene Vorgehensweise für die meisten Benutzer ist die Verwendung des Webinstallers.

Sie können .NET Framework 4.8 in Visual Studio 2012 oder höheren Versionen als Ziel verwenden, indem Sie das [.NET Framework 4.8-Entwicklerpaket](https://go.microsoft.com/fwlink/?LinkId=2085167) installieren.

### <a name="whats-new-in-net-framework-48"></a>Neuerungen in .NET Framework 4.8

.NET Framework 4.8 umfasst neue Features in den folgenden Bereichen:

- [Basisklassen](#core48)
- [Windows Communication Foundation (WCF)](#wcf48)
- [Windows Presentation Foundation (WPF)](#wpf48)
- [Common Language Runtime](#clr48)

Ein Hauptschwerpunkt von .NET Framework 4.8 ist nach wie vor die Verbesserung der Barrierefreiheit, die es einer Anwendung ermöglicht, Benutzern von Hilfstechnologie ein angemessenes Erlebnis zu bieten. Informationen zu Verbesserungen der Barrierefreiheit in .NET Framework 4.8 finden Sie unter [Neuerungen der Barrierefreiheit in .NET Framework](whats-new-in-accessibility.md).

<a name="core48" />

#### <a name="base-classes"></a>Basisklassen

**Reduzierung der Auswirkungen von FIPS auf Kryptografie**. In früheren Versionen von .NET Framework lösen verwaltete Kryptografieanbieterklassen wie <xref:System.Security.Cryptography.SHA256Managed> eine Ausnahme des Typs <xref:System.Security.Cryptography.CryptographicException> aus, wenn die kryptografischen Systembibliotheken im „FIPS-Modus“ konfiguriert sind. Diese Ausnahmen werden ausgelöst, da die verwalteten Versionen der Kryptografieanbieterklassen im Gegensatz zu den kryptografischen Systembibliotheken nicht gemäß FIPS 140-2 (Federal Information Processing Standards) zertifiziert sind. Da nur wenige Entwickler ihre Entwicklungscomputer im FIPS-Modus betreiben, werden die Ausnahmen häufig in Produktionssystemen ausgelöst.

Standardmäßig lösen in diesem Fall die folgenden verwalteten Kryptografieklassen in Anwendungen für .NET Framework 4.8 <xref:System.Security.Cryptography.CryptographicException> nicht mehr aus:

- <xref:System.Security.Cryptography.MD5Cng>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
- <xref:System.Security.Cryptography.RijndaelManaged>
- <xref:System.Security.Cryptography.RIPEMD160Managed>
- <xref:System.Security.Cryptography.SHA256Managed>

Stattdessen leiten diese Klassen kryptografische Vorgänge an eine kryptografische Systembibliothek weiter. Durch diese Änderung wird ein möglicherweise verwirrender Unterschied zwischen Entwicklungs- und Produktionsumgebungen beseitigt, und native Komponenten und verwaltete Komponenten werden gemäß derselben Kryptografierichtlinie ausgeführt. Anwendungen, die von diesen Ausnahmen abhängig sind, können das vorherige Verhalten wiederherstellen, indem sie den AppContext-Schalter `Switch.System.Security.Cryptography.UseLegacyFipsThrow` auf `true` festlegen. Weitere Informationen finden Sie unter [Verwaltete Kryptografieklassen lösen im FIPS-Modus keine CryptographyException aus](../migration-guide/retargeting/4.7.2-4.8.md#managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode).

**Verwendung der aktualisierten Version von ZLib**

Ab .NET Framework 4.5 verwendet die Assembly „clrcompression.dll“ [ZLib](https://www.zlib.net), eine native externe Bibliothek zur Datenkompression, um eine Implementierung für den Verkleinerungsalgorithmus bereitzustellen. In .NET Framework 4.8 wurde „clrcompression.dll“ so aktualisiert, dass die ZLib-Version 1.2.11 verwendet wird, die mehrere wichtige Verbesserungen und Korrekturen enthält.

<a name="wcf48" />

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

**Einführung von ServiceHealthBehavior**

Integritätsendpunkte werden häufig von Orchestrierungstools verwendet, um Dienste basierend auf ihrem Integritätsstatus zu verwalten. Integritätsprüfungen können auch von Überwachungstools eingesetzt werden, um Benachrichtigungen über Verfügbarkeit und Leistung eines Diensts nachzuverfolgen und bereitzustellen.

**ServiceHealthBehavior** ist ein WCF-Dienstverhalten, das <xref:System.ServiceModel.Description.IServiceBehavior> erweitert.  Bei Hinzufügen zur Sammlung <xref:System.ServiceModel.Description.ServiceDescription.Behaviors?displayProperty=nameWithType> bewirkt ein Dienstverhalten Folgendes:

- Gibt Dienstintegritätsstatus mit HTTP-Antwortcodes zurück. Sie können in einer Abfragezeichenfolge den HTTP-Statuscode für eine HTTP/GET-Integritätstestanforderung angeben.

- Informationen zur Dienstintegrität werden veröffentlicht. Dienstspezifische Details, einschließlich Dienststatus, Anzahl der Drosselungen und Kapazität, können durch Verwendung einer HTTP/GET-Anforderung mit der Abfragezeichenfolge `?health` angezeigt werden. Der einfache Zugriff auf solche Informationen ist wichtig, wenn es um die Problembehandlung bei einem fehlerhaften WCF-Dienst geht.

Es gibt zwei Möglichkeiten, den Integritätsendpunkt verfügbar zu machen und Integritätsinformationen des WCF-Diensts zu veröffentlichen:

- Mithilfe von Code. Beispiel:

  ```csharp
  ServiceHost host = new ServiceHost(typeof(Service1),
                     new Uri("http://contoso:81/Service1"));
  ServiceHealthBehavior healthBehavior =
      host.Description.Behaviors.Find<ServiceHealthBehavior>();
  healthBehavior ??= new ServiceHealthBehavior();
  host.Description.Behaviors.Add(healthBehavior);
  ```

  ```vb
  Dim host As New ServiceHost(GetType(Service1),
              New Uri("http://contoso:81/Service1"))
  Dim healthBehavior As ServiceHealthBehavior =
     host.Description.Behaviors.Find(Of ServiceHealthBehavior)()
  If healthBehavior Is Nothing Then
     healthBehavior = New ServiceHealthBehavior()
  End If
  host.Description.Behaviors.Add(healthBehavior)
  ```

- Mithilfe einer Konfigurationsdatei. Beispiel:

  ```xml
  <behaviors>
    <serviceBehaviors>
      <behavior name="DefaultBehavior">
        <serviceHealth httpsGetEnabled="true"/>
      </behavior>
    </serviceBehaviors>
  </behaviors>
  ```

Der Integritätsstatus eines Diensts kann mithilfe von Abfrageparametern wie `OnServiceFailure`, `OnDispatcherFailure`, `OnListenerFailure` und `OnThrottlePercentExceeded` abgefragt werden. Für jeden Abfrageparameter kann ein HTTP-Antwortcode angegeben werden. Wenn der HTTP-Antwortcode für einen Abfrageparameter weggelassen wird, wird standardmäßig der HTTP-Antwortcode 503 verwendet. Beispiel:

- OnServiceFailure: `https://contoso:81/Service1?health&OnServiceFailure=450`

  Der HTTP-Antwortstatuscode 450 wird zurückgegeben, wenn [ServiceHost.State](xref:System.ServiceModel.Channels.CommunicationObject.State) größer als <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType> ist.
Abfrageparameter und Beispiele:

- OnDispatcherFailure: `https://contoso:81/Service1?health&OnDispatcherFailure=455`

  Der HTTP-Antwortstatuscode 455 wird zurückgegeben, wenn der Status eines der Kanalverteiler größer als <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType> ist.

- OnListenerFailure: `https://contoso:81/Service1?health&OnListenerFailure=465`

  Der HTTP-Antwortstatuscode 465 wird zurückgegeben, wenn der Status eines der Kanallistener größer als <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType> ist.

- OnThrottlePercentExceeded: `https://contoso:81/Service1?health&OnThrottlePercentExceeded= 70:350,95:500`

  Gibt den Prozentsatz (1-100) an, der die Antwort und deren HTTP-Antwortcode (200-599) auslöst. In diesem Beispiel:

  - Wenn der Prozentsatz größer als 95 ist, wird der HTTP-Antwortcode 500 zurückgegeben.

  - Wenn der Prozentsatz im Bereich von 70 bis 95 liegt, wird 350 zurückgegeben.

  - Andernfalls wird 200 zurückgegeben.

Der Integritätsstatus des Diensts kann entweder in HTML durch Angeben einer Abfragezeichenfolge wie `https://contoso:81/Service1?health` oder in XML durch Angeben einer Abfragezeichenfolge wie `https://contoso:81/Service1?health&Xml` angezeigt werden. Eine Abfragezeichenfolge wie `https://contoso:81/Service1?health&NoContent` gibt eine leere HTML-Seite zurück.

<a name="wpf48" />

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Verbesserungen bei hohen DPI-Werten**

In .NET Framework 4.8 bietet WPF Kompatibilität mit monitorspezifischen DPI-Werten (V2) und Unterstützung der DPI-Skalierung im gemischten Modus. Weitere Informationen zur Entwicklung mit hohen DPI-Werten finden Sie im Artikel zur [Entwicklung von Desktopanwendungen mit hohen DPI-Werten unter Windows](/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows).

.NET Framework 4.8 bietet eine verbesserte Unterstützung für gehostete HWNDs und die Interoperabilität von Windows Forms in WPF-Anwendungen mit hohen DPI-Werten auf Plattformen, die die DPI-Skalierung im gemischten Modus unterstützen (ab Windows 10-Update vom April 2018). Wenn gehostete HWNDs oder Windows Forms-Steuerelemente als Fenster mit DPI-Skalierung im gemischten Modus durch Aufrufen von [SetThreadDpiHostingBehavior](/windows/desktop/api/winuser/nf-winuser-setthreaddpihostingbehavior) und [SetThreadDpiAwarenessContext](/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext) erstellt werden, können sie in einer WPF-Anwendung mit monitorspezifischen DPI-Werten (V2) gehostet werden und sind entsprechend dimensioniert und skaliert. Solche gehosteten Inhalte werden nicht mit der nativen DPI-Einstellung gerendert, sondern das Betriebssystem skaliert die gehosteten Inhalte auf die geeignete Größe. Die Unterstützung für den mit monitorspezifischen DPI-Werten kompatiblen Modus (V2) ermöglicht das Hosten von WPF-Steuerelementen in einem nativen Fenster in einer Anwendung mit hohen DPI-Werten.

Um die Unterstützung für die Skalierung mit hohen DPI-Werten im gemischten Modus zu aktivieren, können Sie die folgenden [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Schalter in der Anwendungskonfigurationsdatei festlegen:

```xml
<runtime>
   <AppContextSwitchOverrides value = "Switch.System.Windows.DoNotScaleForDpiChanges=false; Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false"/>
</runtime>
```

<a name="clr48" />

#### <a name="common-language-runtime"></a>Common Language Runtime

Die Runtime in .NET Framework 4.8 weist die folgenden Änderungen und Verbesserungen auf:

**Verbesserungen am JIT-Compiler**. Der Just-in-Time-Compiler (JIT) in .NET Framework 4.8 basiert auf dem JIT-Compiler in .NET Core 2.1. Viele der Optimierungen und alle Fehlerkorrekturen für den JIT-Compiler von .NET Core 2.1 sind im JIT-Compiler von .NET Framework 4.8 enthalten.

**Verbesserungen für NGEN**. Die Runtime für die Speicherverwaltung für [Native Image Generator](../tools/ngen-exe-native-image-generator.md)-Bilder (NGEN) wurde so verbessert, dass aus NGEN-Bildern zugeordnete Daten nicht speicherresident sind. Dadurch wird die Angriffsfläche für Versuche, willkürlichen Code auszuführen, verkleinert, indem der auszuführende Speicher modifiziert wird.

**Überprüfung durch Antischadsoftware für alle Assemblys**. In früheren .NET Framework-Versionen scannt die Runtime alle vom Datenträger geladenen Assemblys mit Windows Defender oder Antischadsoftware von Drittanbietern. Assemblys, die aus anderen Quellen geladen werden, z.B. mit der <xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType>-Methode, werden jedoch nicht gescannt und können möglicherweise unentdeckte Schadsoftware enthalten. Ab .NET Framework 4.8 unter Windows 10 löst die Runtime einen Scan durch Antischadsoftware-Lösungen aus, die die [Antimalware Scan Interface (AMSI)](/windows/desktop/AMSI/antimalware-scan-interface-portal) implementieren.

<a name="v472" />

## <a name="whats-new-in-net-framework-472"></a>Neuerungen in .NET Framework 4.7.2

.NET Framework 4.7.2 umfasst neue Features in den folgenden Bereichen:

- [Basisklassen](#core-472)
- [ASP.NET](#asp-net472)
- [Netzwerk](#net472)
- [SQL](#sql472)
- [WPF](#wpf472)
- [ClickOnce](#clickonce)

Ein Hauptschwerpunkt von .NET Framework 4.7.2 ist nach wie vor die Verbesserung der Barrierefreiheit, die es einer Anwendung ermöglicht, Benutzern von Hilfstechnologie ein angemessenes Erlebnis zu bieten. Informationen zu Verbesserungen der Barrierefreiheit in .NET Framework 4.7.2 finden Sie unter [Neuerungen der Barrierefreiheit in .NET Framework](whats-new-in-accessibility.md).

<a name="core-472" />

#### <a name="base-classes"></a>Basisklassen

.NET Framework 4.7.2 bietet eine große Anzahl kryptografischer Optimierungen, bessere Unterstützung der Dekomprimierung von ZIP-Archiven und zusätzliche Sammlungs-APIs.

**Neue Überladungen von RSA.Create und DSA.Create**

Mit den <xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType>- und <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>-Methoden können Sie Schlüsselparameter bei der Instanziierung eines neuen <xref:System.Security.Cryptography.DSA>- oder <xref:System.Security.Cryptography.RSA>-Schlüssels bereitstellen. Damit können Sie Code wie den folgenden:

```csharp
// Before .NET Framework 4.7.2
using (RSA rsa = RSA.Create())
{
   rsa.ImportParameters(rsaParameters);
   // Other code to execute using the RSA instance.
}
```

```vb
' Before .NET Framework 4.7.2
Using rsa = RSA.Create()
   rsa.ImportParameters(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

durch solchen Code ersetzen:

```csharp
// Starting with .NET Framework 4.7.2
using (RSA rsa = RSA.Create(rsaParameters))
{
   // Other code to execute using the rsa instance.
}
```

```vb
' Starting with .NET Framework 4.7.2
Using rsa = RSA.Create(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

Mit den <xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType>- und <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType>-Methoden können Sie neue <xref:System.Security.Cryptography.DSA>- oder <xref:System.Security.Cryptography.RSA>-Schlüssel mit einer bestimmten Schlüsselgröße generieren. Beispiel:

```csharp
using (DSA dsa = DSA.Create(2048))
{
   // Other code to execute using the dsa instance.
}
```

```vb
Using dsa = DSA.Create(2048)
   ' Other code to execute using the dsa instance.
End Using
```

**Rfc2898DeriveBytes-Konstruktoren akzeptieren einen Hashalgorithmusnamen**

Die <xref:System.Security.Cryptography.Rfc2898DeriveBytes>-Klasse verfügt über drei neue Konstruktoren mit einem <xref:System.Security.Cryptography.HashAlgorithmName>-Parameter, der den beim Ableiten von Schlüsseln zu verwendenden HMAC-Algorithmus identifiziert. Anstatt SHA-1 zu verwenden, sollten Entwickler einen auf SHA-2 basierenden HMAC-Algorithmus wie SHA-256 verwenden. Das folgende Beispiel zeigt dies:

```csharp
private static byte[] DeriveKey(string password, out int iterations, out byte[] salt,
                                out HashAlgorithmName algorithm)
{
   iterations = 100000;
   algorithm = HashAlgorithmName.SHA256;

   const int SaltSize = 32;
   const int DerivedValueSize = 32;

   using (Rfc2898DeriveBytes pbkdf2 = new Rfc2898DeriveBytes(password, SaltSize,
                                                             iterations, algorithm))
   {
      salt = pbkdf2.Salt;
      return pbkdf2.GetBytes(DerivedValueSize);
   }
}
```

```vb
Private Shared Function DeriveKey(password As String, ByRef iterations As Integer,
                                  ByRef salt AS Byte(), ByRef algorithm As HashAlgorithmName) As Byte()
   iterations = 100000
   algorithm = HashAlgorithmName.SHA256

   Const SaltSize As Integer = 32
   Const  DerivedValueSize As Integer = 32

   Using pbkdf2 = New Rfc2898DeriveBytes(password, SaltSize, iterations, algorithm)
      salt = pbkdf2.Salt
      Return pbkdf2.GetBytes(DerivedValueSize)
   End Using
End Function
```

**Unterstützung für kurzlebige Schlüssel**

Der PFX-Import kann optional private Schlüssel direkt aus dem Arbeitsspeicher unter Umgehung der Festplatte laden. Wenn das neue <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType>-Flag in einem <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Konstruktor oder einer der Überladungen der <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType>-Methode angegeben wird, werden die privaten Schlüssel als kurzlebige Schlüssel geladen. Auf diese Weise wird verhindert, dass die Schlüssel auf dem Datenträger sichtbar sind. Dabei gilt jedoch Folgendes:

- Da die Schlüssel nicht dauerhaft auf dem Datenträger gespeichert werden, sind Zertifikate, die mit diesem Flag geladen werden, keine guten Kandidaten zum Hinzufügen zu einem X509Store.

- Auf diese Weise geladene Schlüssel werden fast immer über Windows CNG geladen. Aus diesem Grund müssen Aufrufer auf den privaten Schlüssel zugreifen, indem sie Erweiterungsmethoden wie z.B. [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A) aufrufen. Die <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>-Eigenschaft funktioniert nicht.

- Da die <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>-Legacyeigenschaft nicht mit Zertifikaten funktioniert, sollten Entwickler strenge Tests vor dem Umstieg auf kurzlebige Schlüssel ausführen.

**Programmgesteuertes Erstellen von PKCS#10-Zertifizierungssignaturanforderungen und X.509-Zertifikaten mit öffentlichen Schlüsseln**

Ab .NET Framework 4.7.2 können Workloads Zertifikatsignaturanforderungen generieren, die das Staging der Generierung von Zertifikatsanforderung in vorhandenen Tools ermöglichen. Dies ist insbesondere in Testszenarien nützlich.

Weitere Informationen und Codebeispiele finden Sie unter „Programmgesteuertes Erstellen von PKCS#10-Zertifikatsignaturanforderungen und X.509-Zertifikaten mit öffentlichen Schlüsseln“ im [.NET-Blog](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Neue SignerInfo-Member**

Ab .NET Framework 4.7.2 stellt die <xref:System.Security.Cryptography.Pkcs.SignerInfo>-Klasse weitere Informationen zur Signatur bereit. Sie können den Wert der <xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName>-Eigenschaft abrufen, um den vom Signaturgeber verwendeten Signaturalgorithmus zu bestimmen. <xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType> kann aufgerufen werden, um eine Kopie der kryptografischen Signatur für diesen Signaturgeber abzurufen.

**Beibehalten der Öffnung eines in einem Wrapper enthaltenen Datenstroms nach dem Verwerfen von CryptoStream**

Ab .NET Framework 4.7.2 verfügt die <xref:System.Security.Cryptography.CryptoStream>-Klasse über einen zusätzlichen Konstruktor, der es <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> ermöglicht, den in einem Wrapper enthaltenen Datenstrom nicht zu schließen. Um den in einem Wrapper enthaltenen Datenstrom nach dem Verwerfen der <xref:System.Security.Cryptography.CryptoStream>-Instanz geöffnet zu lassen, rufen Sie den neuen <xref:System.Security.Cryptography.CryptoStream>-Konstruktor wie folgt auf:

```csharp
var cStream = new CryptoStream(stream, transform, mode, leaveOpen: true);
```

```vb
Dim cStream = New CryptoStream(stream, transform, mode, leaveOpen:=true)
```

**Dekomprimierungsänderungen in DeflateStream**

Ab .NET Framework 4.7.2 hat sich die Implementierung der Dekomprimierungsvorgänge in der <xref:System.IO.Compression.DeflateStream>-Klasse so geändert, dass standardmäßig native Windows-APIs verwendet werden. In der Regel führt dies zu einer beträchtlichen Leistungssteigerung.

Unterstützung für Dekomprimierung mithilfe von Windows-APIs ist standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.2 als Ziel verwenden. Anwendungen, die für frühere Versionen von .NET Framework gedacht sind, aber unter .NET Framework 4.7.2 ausgeführt werden, können dieses Verhalten übernehmen, indem der folgende [AppContext-Schalter](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) der Anwendungskonfigurationsdatei hinzugefügt wird:

```xml
<AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=false" />
```

**Zusätzliche Sammlungs-APIs**

.NET Framework 4.7.2 fügt den Typen <xref:System.Collections.Generic.SortedSet%601> und <xref:System.Collections.Generic.HashSet%601> eine Reihe neuer APIs hinzu. Dazu gehören:

- `TryGetValue`-Methoden, die das try-Muster, das in anderen Sammlungstypen verwendet wird, auf diese beiden Typen erweitern. Dabei handelt es sich um folgenden Methoden:

  - [public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)
  - [public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)

- `Enumerable.To*`-Erweiterungsmethoden, die eine Sammlung in ein <xref:System.Collections.Generic.HashSet%601> konvertieren:

  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)](xref:System.Linq.Enumerable.ToHashSet%2A)
  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)](xref:System.Linq.Enumerable.ToHashSet%2A)

- Neue <xref:System.Collections.Generic.HashSet%601>-Konstruktoren, mit denen Sie die Kapazität der Sammlung festlegen können. Dies führt zu einem Leistungsvorteil, wenn Sie die Größe von <xref:System.Collections.Generic.HashSet%601> im voraus kennen:

  - [public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))
  - [public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))

Die <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Klasse enthält neue Überladungen der <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>- und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>-Methoden zum Abrufen eines Werts aus dem Wörterbuch oder zum Hinzufügen eines Werts, wenn kein Wert gefunden wurde, sowie zum Hinzufügen eines Werts zum Wörterbuch bzw. zum Aktualisieren des Werts, wenn dieser bereits vorhanden ist.

```csharp
public TValue AddOrUpdate<TArg>(TKey key, Func<TKey, TArg, TValue> addValueFactory, Func<TKey, TValue, TArg, TValue> updateValueFactory, TArg factoryArgument)

public TValue GetOrAdd<TArg>(TKey key, Func<TKey, TArg, TValue> valueFactory, TArg factoryArgument)
```

```vb
Public AddOrUpdate(Of TArg)(key As TKey, addValueFactory As Func(Of TKey, TArg, TValue), updateValueFactory As Func(Of TKey, TValue, TArg, TValue), factoryArgument As TArg) As TValue

Public GetOrAdd(Of TArg)(key As TKey, valueFactory As Func(Of TKey, TArg, TValue), factoryArgument As TArg) As TValue
```

<a name="asp-net472" />

#### <a name="aspnet"></a>ASP.NET

**Unterstützung für Abhängigkeitsinjektion in Web Forms**

[Abhängigkeitsinjektion (Dependency Injection, DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) entkoppelt Objekte und ihre Abhängigkeiten, sodass der Code eines Objekts nicht mehr geändert werden muss, nur weil sich eine Abhängigkeit geändert hat. Beim Entwickeln von ASP.NET-Anwendungen für .NET Framework 4.7.2 haben Sie folgende Möglichkeiten:

- Verwenden von setterbasierter, schnittstellenbasierter und konstruktorbasierter Injektion in [Handler und Module](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [Seiteninstanzen](xref:System.Web.UI.Page) und [Benutzersteuerelemente](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) von ASP.NET-Webanwendungsprojekten.

- Verwenden von setterbasierter und schnittstellenbasierter Injektion in [Handler und Module](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [Seiteninstanzen](xref:System.Web.UI.Page) und [Benutzersteuerelemente](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) von ASP.NET-Websiteprojekten.

- Einbinden verschiedener Abhängigkeitsinjektionsframeworks.

**Unterstützung für SameSite-Cookies**

[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) verhindert, dass ein Browser ein Cookie zusammen mit einer standortübergreifenden Anforderung sendet. .NET Framework 4.7.2 fügt eine <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType>-Eigenschaft hinzu, deren Wert ein Member der <xref:System.Web.SameSiteMode?displayProperty=nameWithType>-Enumeration ist. Wenn der Wert <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> oder <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType> ist, fügt ASP.NET dem set-cookie-Header das `SameSite`-Attribut hinzu. SameSite-Unterstützung gilt für <xref:System.Web.HttpCookie>-Objekte sowie für <xref:System.Web.Security.FormsAuthentication>- und <xref:System.Web.SessionState>-Cookies.

Sie können SameSite für ein <xref:System.Web.HttpCookie>-Objekt wie folgt festlegen:

```csharp
var c = new HttpCookie("secureCookie", "same origin");
c.SameSite = SameSiteMode.Lax;
```

```vb
Dim c As New HttpCookie("secureCookie", "same origin")
c.SameSite = SameSiteMode.Lax
```

Sie können auch SameSite-Cookies auf Anwendungsebene konfigurieren, indem Sie die Datei „web.config“ ändern:

```xml
<system.web>
   <httpCookies sameSite="Strict" />
</system.web>
```

Sie können SameSite für <xref:System.Web.Security.FormsAuthentication>- und <xref:System.Web.SessionState>-Cookies hinzufügen, indem Sie die Datei „web.config“ ändern:

```xml
<system.web>
   <authentication mode="Forms">
      <forms cookieSameSite="Lax">
         <!-- ...   -->
      </forms>
   <authentication />
   <sessionState cookieSameSite="Lax"></sessionState>
</system.web>
```

<a name="net472" />

#### <a name="networking"></a>Netzwerk

**Implementierung von HttpClientHandler-Eigenschaften**

.NET Framework 4.7.1 hat der <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>-Klasse acht Eigenschaften hinzugefügt. Allerdings haben zwei davon eine <xref:System.PlatformNotSupportedException> ausgelöst. .NET Framework 4.7.2 bietet jetzt eine Implementierung für diese Eigenschaften. Dabei handelt es sich um die folgenden Eigenschaften:

- <xref:System.Net.Http.HttpClientHandler.CheckCertificateRevocationList>
- <xref:System.Net.Http.HttpClientHandler.SslProtocols>

<a name="sql472" />

#### <a name="sqlclient"></a>SQLClient

**Unterstützung für universelle Azure Active Directory-Authentifizierung und mehrstufige Authentifizierung**

Wachsende Konformitäts- und Sicherheitsanforderungen verlangen, dass zahlreiche Kunden mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) verwenden. Darüber hinaus raten bewährte Methoden davon ab, Benutzerkennwörter direkt in Verbindungszeichenfolgen einzubinden. Um diese Änderungen zu unterstützen, erweitert .NET Framework 4.7.2 [SQLClient-Verbindungszeichenfolgen](xref:System.Data.SqlClient.SqlConnection.ConnectionString) durch Hinzufügen eines neuen Werts („Active Directory Interactive“) für das vorhandene Schlüsselwort „Authentication“ zur Unterstützung von MFA und [Azure AD-Authentifizierung](/azure/sql-database/sql-database-aad-authentication-configure). Die neue interaktive Methode unterstützt native und Azure AD-Verbundbenutzer sowie Azure AD-Gastbenutzer. Wenn diese Methode verwendet wird, wird die von Azure AD verlangte MFA-Authentifizierung für SQL-Datenbanken unterstützt. Darüber hinaus fordert der Authentifizierungsprozess ein Benutzerkennwort an, um bewährten Sicherheitsmethoden zu genügen.

In früheren Versionen von .NET Framework unterstützte die SQL-Konnektivität nur die <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType>- und <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType>-Optionen. Beide Optionen sind Teil des nicht interaktiven [ADAL Protokolls](/azure/active-directory/develop/active-directory-authentication-libraries), das MFA nicht unterstützt. Mit der neuen <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType>-Option unterstützt die SQL-Konnektivität MFA sowie vorhandene Authentifizierungsmethoden (Kennwort und integrierte Authentifizierung). Dies ermöglicht Benutzern die interaktive Eingabe von Benutzerkennwörtern ohne Speichern von Kennwörtern in der Verbindungszeichenfolge.

Weitere Informationen und ein Beispiel finden Sie unter „SQL: Unterstützung für universelle Azure AD- und mehrstufige Authentifizierung“ im [.NET-Blog](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Unterstützung für Always Encrypted, Version 2**

NET Framework 4.7.2 fügt Unterstützung für Enclave-basiertes Always Encrypted hinzu. Die ursprüngliche Version von Always Encrypted ist eine clientseitige Verschlüsselungstechnologie, bei der die Verschlüsselungsschlüssel den Client nie verlassen. Im Enclave-basierten Always Encrypted kann der Client optional die Verschlüsselungsschlüssel an eine sichere Enclave senden. Dabei handelt es sich um eine sichere Computerentität, die als Teil von SQL Server betrachtet, aber nicht durch SQL Server-Code manipuliert werden kann. Zur Unterstützung von Enclave-basiertem Always Encrypted fügt .NET Framework 4.7.2 dem <xref:System.Data.SqlClient>-Namespace die folgenden Typen und Member hinzu:

- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType>: Gibt den URI für Enclave-basiertes Always Encrypted an.

- <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider>: Eine abstrakte Klasse, von der alle Enclave-Anbieter abgeleitet werden.

- <xref:System.Data.SqlClient.SqlEnclaveSession>: Kapselt den Zustand für eine bestimmte Enclave-Sitzung.

- <xref:System.Data.SqlClient.SqlEnclaveAttestationParameters>: Stellt die Nachweisparameter bereit, die von SQL Server zum Abrufen von Informationen verwendet werden, die zum Ausführen eines bestimmten Protokolls erforderlich sind.

Die Anwendungskonfigurationsdatei gibt dann eine konkrete Implementierung der abstrakten <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType>-Klasse an, die die Funktionalität für den Enclave-Anbieter bereitstellt. Beispiel:

```xml
<configuration>
  <configSections>
    <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/> 
  </configSections>
  <SqlColumnEncryptionEnclaveProviders>
    <providers>
      <add name="Azure" type="Microsoft.SqlServer.Management.AlwaysEncrypted.AzureEnclaveProvider,MyApp"/>
      <add name="HGS" type="Microsoft.SqlServer.Management.AlwaysEncrypted.HGSEnclaveProvider,MyApp" />
    </providers>
  </SqlColumnEncryptionEnclaveProviders >
</configuration>
```

Dies ist der grundlegende Ablauf von Enclave-basiertem Always Encrypted:

1. Der Benutzer erstellt eine AlwaysEncrypted-Verbindung mit SQL Server, die Enclave-basiertes Always Encrypted unterstützt. Der Treiber kontaktiert den Nachweisdienst, um sicherzustellen, dass er eine Verbindung mit der richtigen Enclave herstellt.

1. Sobald die Enclave bestätigt wurde, richtet der Treiber einen sicheren Kanal ein, wobei die sichere Enclave unter SQL Server gehostet wird.

1. Der Treiber verwendet vom Client autorisierte Verschlüsselungsschlüssel für die Dauer der SQL-Verbindung mit der sicheren Enclave gemeinsam.

<a name="wpf472" />

#### <a name="windows-presentation-foundation"></a>Windows Presentation Foundation

**Suchen nach ResourceDictionaries nach Quelle**

Ab .NET Framework 4.7.2 kann ein Diagnose-Assistent die  <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries> suchen, die für einen bestimmten Quell-URI erstellt wurden. (Dieses Feature steht für die Verwendung durch Diagnose Assistenten zur Verfügung, nicht für Produktionsanwendungen.) Ein Diagnose-Assistent (z.B. die Visual Studio-Funktion „Bearbeiten und fortfahren“) erlaubt es dem Benutzer, ein ResourceDictionary mit der Absicht zu bearbeiten, dass die Änderungen auf die aktuell ausgeführte Anwendung angewendet werden. Ein Schritt zum Erreichen dieses Ziels besteht im Ermitteln aller ResourceDictionaries, die die ausgeführte Anwendung aus dem Wörterbuch erstellt hat, das aktuell bearbeitet wird. Beispielsweise kann eine Anwendung ein ResourceDictionary deklarieren, dessen Inhalt aus einem bestimmten Quell-URI kopiert wird:

```xml
<ResourceDictionary Source="MyRD.xaml">
```

Ein Diagnose-Assistent, der das ursprüngliche Markup in *MyRD.xaml*  bearbeitet, kann das neue Feature verwenden, um nach dem Wörterbuch zu suchen. Das Feature wird durch eine neue statische Methode (<xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>) implementiert. Der Diagnose-Assistent ruft die neue Methode über einen absoluten URI auf, der das ursprüngliche Markup identifiziert, wie der folgende Code veranschaulicht:

```csharp
IEnumerable<ResourceDictionary> dictionaries = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(new Uri("pack://application:,,,/MyApp;component/MyRD.xaml"));
```

```vb
Dim dictionaries As IEnumerable(Of ResourceDictionary) = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(New Uri("pack://application:,,,/MyApp;component/MyRD.xaml"))
```

Die Methode gibt ein leeres aufzählbares Element zurück, es sei denn,  <xref:System.Windows.Diagnostics.VisualDiagnostics> ist aktiviert, und die [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) -Umgebungsvariable wurde festgelegt.

**Suchen nach ResourceDictionary-Besitzern**

Ab .NET Framework 4.7.2 kann ein Diagnose-Assistent die Besitzer eines bestimmten <xref:Windows.UI.Xaml.ResourceDictionary> ermitteln. (Das Feature steht für die Verwendung durch Diagnose Assistenten und nicht durch Produktionsanwendungen zur Verfügung.) Wenn eine Änderung an einem <xref:Windows.UI.Xaml.ResourceDictionary> vorgenommen wird, ermittelt WPF automatisch alle [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md)-Verweise, die von der Änderung betroffen sein könnten.

Ein Diagnose-Assistenten wie etwa die Funktion „Bearbeiten und fortfahren“ von Visual Studio kann diese Funktion ggf. erweitern, um [StaticResource](../wpf/advanced/staticresource-markup-extension.md)-Verweise zu verarbeiten. Der erste Schritt in diesem Prozess ist das Ermitteln der Besitzer des Wörterbuchs, also aller Objekte, deren `Resources`-Eigenschaft auf das Wörterbuch verweist (entweder direkt oder indirekt über die <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType>-Eigenschaft). Drei neue statische Methoden, die für die <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType>-Klasse implementiert wurden (jeweils eine Methode für jeden der Basistypen, der über eine `Resources`-Eigenschaft verfügt), unterstützen diesen Schritt:

- [`public static IEnumerable<FrameworkElement> GetFrameworkElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkElementOwners%2A)

- [`public static IEnumerable<FrameworkContentElement> GetFrameworkContentElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkContentElementOwners%2A)

- [`public static IEnumerable<Application> GetApplicationOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetApplicationOwners%2A)

Diese Methoden geben ein leeres aufzählbares Element zurück, es sei denn,  <xref:System.Windows.Diagnostics.VisualDiagnostics> ist aktiviert, und die [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) -Umgebungsvariable wurde festgelegt.

**Suchen nach StaticResource-Verweisen**

Ein Diagnose-Assistent kann jetzt immer dann eine Benachrichtigung erhalten, wenn ein [StaticResource](../wpf/advanced/staticresource-markup-extension.md)-Verweis aufgelöst wird. (Das Feature steht für die Verwendung durch Diagnose Assistenten zur Verfügung, nicht für Produktionsanwendungen.) Ein Diagnose-Assistent wie etwa die Funktion „Bearbeiten und fortfahren“ von Visual Studio möchte ggf. alle Verwendungen einer Ressource aktualisieren, wenn sich ihr Wert in einem <xref:Windows.UI.Xaml.ResourceDictionary> ändert. WPF führt dies automatisch für [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md)-Verweise aus, aber absichtlich nicht für [StaticResource](../wpf/advanced/staticresource-markup-extension.md)-Verweise. Ab .NET Framework 4.7.2 kann der Diagnose-Assistent diese Benachrichtigungen verwenden, um diese Verwendungen der statischen Ressource zu ermitteln.

Die Benachrichtigung wird durch das neue <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType>-Ereignis implementiert:

```csharp
public static event EventHandler<StaticResourceResolvedEventArgs> StaticResourceResolved;
```

```vb
Public Shared Event StaticResourceResolved As EventHandler(Of StaticResourceResolvedEventArgs)
```

Dieses Ereignis wird immer ausgelöst, wenn die Runtime einen [StaticResource](../wpf/advanced/staticresource-markup-extension.md)-Verweis auflöst. Die <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs>-Argumente beschreiben die Auflösung und geben das Objekt und die Eigenschaft an, die den [StaticResource](../wpf/advanced/staticresource-markup-extension.md)-Verweis hosten, sowie das  <xref:Windows.UI.Xaml.ResourceDictionary> und den Schlüssel, die für die Auflösung verwendet wurden:

```csharp
public class StaticResourceResolvedEventArgs : EventArgs
{
   public Object TargetObject { get; }

   public Object TargetProperty { get; }

   public ResourceDictionary ResourceDictionary { get; }

   public object ResourceKey { get; }
}
```

```vb
Public Class StaticResourceResolvedEventArgs : Inherits EventArgs
   Public ReadOnly Property TargetObject As Object
   Public ReadOnly Property TargetProperty As Object
   Public ReadOnly Property ResourceDictionary As ResourceDictionary
   Public ReadOnly Property ResourceKey As Object
End Class
```

Das Ereignis wird nicht ausgelöst (und sein `add`-Accessor wird ignoriert), es sei denn,  <xref:System.Windows.Diagnostics.VisualDiagnostics> ist aktiviert und die [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) -Umgebungsvariable wurde festgelegt.

#### <a name="clickonce"></a>ClickOnce

HDPI-fähige Anwendungen für Windows Forms, Windows Presentation Foundation (WPF) und Visual Studio-Tools für Office (VSTO) können alle mithilfe von ClickOnce bereitgestellt werden. Wenn der folgende Eintrag im Anwendungsmanifest gefunden wird, ist die Bereitstellung unter .NET Framework 4.7.2 erfolgreich:

```xml
<windowsSettings>
   <dpiAware xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">true</dpiAware>
</windowsSettings>
```

Für eine Windows Forms-Anwendung ist die vorherige Problemumgehung durch Festlegen der DPI-Fähigkeit in der Anwendungskonfigurationsdatei anstatt im Anwendungsmanifest nicht mehr erforderlich, damit die ClickOnce-Bereitstellung erfolgreich ist.

<a name="v471" />

## <a name="whats-new-in-net-framework-471"></a>Neuerungen in .NET Framework 4.7.1

.NET Framework 4.7.1 umfasst neue Features in den folgenden Bereichen:

- [Basisklassen](#core471)
- [Common Language Runtime (CLR)](#clr)
- [Netzwerk](#net471)
- [ASP.NET](#asp-net471)

Ein Hauptschwerpunkt von .NET Framework 4.7.1 ist außerdem die Verbesserung der Barrierefreiheit, die es einer Anwendung ermöglicht, Benutzern von Hilfstechnologie ein angemessenes Erlebnis zu bieten. Informationen zu Verbesserungen der Barrierefreiheit in .NET Framework 4.7.1 finden Sie unter [Neuerungen der Barrierefreiheit in .NET Framework](whats-new-in-accessibility.md).

<a name="core471" />

#### <a name="base-classes"></a>Basisklassen

**Unterstützung für .NET Standard 2.0**

[.NET Standard](../../standard/net-standard.md) definiert einen Satz von APIs, die in jeder .NET Implementierung verfügbar sein müssen, die diese Version des Standards unterstützt. .NET Framework 4.7.1 unterstützt den .NET Standard 2.0 vollständig und fügt [etwa 200 APIs](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt) hinzu, die in .NET Standard 2.0 definiert sind und in .NET Framework 4.6.1, 4.6.2 und 4.7 fehlen. (Beachten Sie, dass diese Versionen von .NET Framework .NET Standard 2.0 nur dann unterstützen, wenn zusätzliche .NET Standard-Unterstützungsdateien auch auf dem Zielsystem bereitgestellt werden.) Weitere Informationen finden Sie unter „BCL: Unterstützung für .NET 2.0 Standard“ im Blogbeitrag zu [.NET Framework 4.7.1 Runtime und Compilerfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/).

**Unterstützung für Konfiguratiosgeneratoren**

Konfigurationsgeneratoren ermöglichen es Entwicklern, Konfigurationseinstellungen für Anwendungen dynamisch zur Laufzeit einzufügen und zu erstellen. Benutzerdefinierte Konfigurationsgeneratoren können verwendet werden, um vorhandene Daten in einem Konfigurationsabschnitt zu ändern oder einen Konfigurationsabschnitt ganz neu zu erstellen. Ohne Konfigurationsgeneratoren sind CONFIG-Dateien statisch, und ihre Einstellungen werden einige Zeit vor dem Start einer Anwendung festgelegt.

Um einen benutzerdefinierten Konfigurationsgenerator zu erstellen, leiten Sie Ihren Generator von der abstrakten <xref:System.Configuration.ConfigurationBuilder>-Klasse ab und überschreiben seine <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType>- und <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>-Elemente. Außerdem definieren Sie Ihre Generatoren in der CONFIG-Datei. Weitere Informationen finden Sie im Abschnitt „Konfigurationsgeneratoren“ im Blogbeitrag zu [.NET Framework 4.7.1 ASP.NET und Konfigurationsfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/).

**Featureerkennung zur Laufzeit**

Die <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType>-Klasse stellt einen Mechanismus zur Verfügung, mit dem festgestellt werden kann, ob ein vordefiniertes Feature für eine bestimmte .NET-Implementierung zur Kompilierungszeit oder zur Laufzeit unterstützt wird. Zur Kompilierungszeit kann ein Compiler überprüfen, ob ein angegebenes Feld vorhanden ist, um festzustellen, ob das Merkmal unterstützt wird. Ist dies der Fall, kann er Code ausgeben, der dieses Merkmal nutzt. Zur Laufzeit kann eine Anwendung die Methode <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> aufrufen, bevor zur Laufzeit Code ausgegeben wird. Weitere Informationen finden Sie unter [Hinzufügen einer Hilfsmethode, um Features zu beschreiben, die von der Laufzeit unterstützt werden](https://github.com/dotnet/corefx/issues/17116).

**Werttupeltypen sind serialisierbar**

Ab .NET Framework 4.7.1 werden <xref:System.ValueTuple?displayProperty=nameWithType> und die zugehörigen generischen Typen als [serialisierbar](xref:System.SerializableAttribute) markiert, was eine binäre Serialisierung ermöglicht. Dies sollte das Migrieren von Tupeltypen (z.B. <xref:System.Tuple%603> und <xref:System.Tuple%604>) zu Werttupeltypen vereinfachen. Weitere Informationen finden Sie unter „Compiler: ValueTuple ist serialisierbar“ im Blogbeitrag zu [.NET Framework 4.7.1 Runtime und Compilerfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/).

**Unterstützung für schreibgeschützte Verweise**

.NET Framework 4.7.1 wurde das <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType> hinzugefügt. Dieses Attribut wird von Sprachcompilern verwendet, um Member mit schreibgeschützten ref-Rückgabetypen oder -Parametern zu kennzeichnen. Weitere Informationen finden Sie unter „Compiler: Unterstützung für ReadOnlyReferences“ im Blogbeitrag zu [.NET Framework 4.7.1 Runtime und Compilerfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/). Weitere Informationen zu ref-Rückgabewerten finden Sie unter [Ref-Rückgabewerte und lokale ref-Variablen (C#-Leitfaden)](../../csharp/programming-guide/classes-and-structs/ref-returns.md) und [Ref-Rückgabewerte (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md).

<a name="clr" />

#### <a name="common-language-runtime-clr"></a>Common Language Runtime (CLR)

**Leistungsverbesserungen für Garbage Collection**

Änderungen an der Garbage Collection (GC) in .NET Framework 4.7.1 verbessern die Gesamtleistung, insbesondere bei LOH-Zuweisungen (Large Object Heap). In .NET Framework 4.7.1 werden separate Sperren für SOH- (Small Object Heap) und LOH-Zuweisungen verwendet, die es ermöglichen, dass LOH-Zuweisungen auftreten, wenn Garbage Collection im Hintergrund den SOH bereinigt. Folglich sollten Anwendungen, die eine große Anzahl von LOH-Zuweisungen vornehmen, eine Verringerung der Zuweisungssperrenkonflikte und eine verbesserte Leistung erfahren. Weitere Informationen finden Sie im Abschnitt „Runtime: Leistungsverbesserungen der Garbage Collection" im Blogbeitrag zu [.NET Framework 4.7.1 Runtime und Compilerfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/).

<a name="net471"/>

#### <a name="networking"></a>Netzwerk

**SHA-2-Unterstützung für Message.HashAlgorithm**

In .NET Framework 4.7 und früheren Versionen unterstützte die <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType>-Eigenschaft nur die Werte <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> und <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType>. Ab .NET Framework 4.7.1 werden <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType>, und <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType> ebenfalls unterstützt. Ob dieser Wert tatsächlich verwendet wird, hängt von MSMQ ab, da die <xref:System.Messaging.Message>-Instanz selbst kein Hashing ausführt, sondern einfach Werte an MSMQ übergibt. Weitere Informationen finden Sie im Abschnitt „SHA-2-Unterstützung für Message.HashAlgorithm“ im Blogbeitrag zu [.NET Framework 4.7.1 ASP.NET und Konfigurationsfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/).

<a name="asp-net471" />

#### <a name="aspnet"></a>ASP.NET

**Ausführungsschritte in ASP.NET-Anwendungen**

ASP.NET verarbeitet Anforderungen in einer vordefinierten Pipeline, die 23 Ereignisse umfasst. ASP.NET führt jeden Ereignishandler als einen Ausführungsschritt aus. In Versionen von ASP.NET bis zu .NET Framework 4.7 kann ASP.NET den Ausführungskontext aufgrund des Wechsels zwischen nativen und verwalteten Threads nicht durchlaufen. Stattdessen durchläuft ASP. NET selektiv nur den <xref:System.Web.HttpContext>. Ab .NET Framework 4.7.1 ermöglicht die <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType>-Methode auch die Wiederherstellung von Umgebungsdaten durch Module. Dieses Feature richtet sich an Bibliotheken, die sich mit der Ablaufverfolgung, Profilerstellung, Diagnose oder Transaktionen befassen, die beispielsweise den Ausführungsablauf der Anwendung übernehmen. Weitere Informationen finden Sie unter „ASP.NET-Feature Ausführungsschritt“ im Blogbeitrag zu [.NET Framework 4.7.1 ASP.NET und Konfigurationsfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/).

**HttpCookie-Analyse von ASP.NET**

.NET Framework 4.7.1 enthält eine neue Methode (<xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>), die eine standardisierte Möglichkeit bietet, ein <xref:System.Web.HttpCookie>-Objekt aus einer Zeichenfolge zu erstellen und Cookiewerte wie das Ablaufdatum und den Pfad genau zuzuweisen. Weitere Informationen finden Sie unter „HttpCookie-Analyse von ASP.NET“ im Blogbeitrag zu [.NET Framework 4.7.1 ASP.NET und Konfigurationsfeatures](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/).

**SHA-2-Hashoptionen für Anmeldeinformationen für formularbasierte Authentifizierung von ASP.NET**

In .NET Framework 4.7 und früheren Versionen erlaubte ASP.NET Entwicklern, Benutzeranmeldeinformationen mit Kennwörtern mit Hashes in Konfigurationsdateien unter Verwendung von MD5 oder SHA1 zu speichern. Ab .NET Framework 4.7.1 unterstützt ASP.NET auch die neuen, sicheren SHA-2-Hashoptionen wie etwa SHA256, SHA384 und SHA512. SHA1 bleibt die Standardeinstellung, und ein nicht standardmäßiger Hashalgorithmus kann in der Webkonfigurationsdatei definiert werden. Beispiel:

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47" />

## <a name="whats-new-in-net-framework-47"></a>Neuerungen in .NET Framework 4.7

.NET Framework 4.7 umfasst neue Features in den folgenden Bereichen:

- [Basisklassen](#Core47)
- [Netzwerk](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Eine Liste der neuen APIs, die .NET Framework 4.7 hinzugefügt wurden, finden Sie unter [API-Änderungen für .NET Framework 4.7](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) auf GitHub. Eine Liste der Verbesserungen von Features und Fehlerkorrekturen in .NET Framework 4.7 finden Sie unter [Liste mit Änderungen für .NET Framework 4.7](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) auf GitHub.  Weitere Informationen finden Sie unter [Ankündigung von .NET Framework 4.7](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/) im .NET-Blog.

<a name="Core47" />

#### <a name="base-classes"></a>Basisklassen

.NET Framework 4.7 verbessert die Serialisierung durch die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Verbesserte Funktionalität mit Elliptic Curve Cryptography (ECC)***

In .NET Framework 4.7 wurden `ImportParameters(ECParameters)`-Methoden den Klassen <xref:System.Security.Cryptography.ECDsa> und <xref:System.Security.Cryptography.ECDiffieHellman> hinzugefügt, damit ein Objekt einen bereits eingerichteten Schlüssel darstellen kann. Eine `ExportParameters(Boolean)`-Methode wurde auch zum Exportieren des Schlüssels unter Verwendung expliziter Kurvenparameter hinzugefügt.

.NET Framework 4.7 unterstützt nun auch zusätzliche Kurven (einschließlich der Brainpool-Kurvengruppe) und bietet vordefinierte Definitionen zur Erleichterung der Erstellung mithilfe der Factorymethoden <xref:System.Security.Cryptography.ECDsa.Create%2A> und <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

Auf GitHub finden Sie ein [Beispiel der kryptografischen Verbesserungen in .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e).

**Bessere Unterstützung für Steuerzeichen durch DataContractJsonSerializer**

In .NET Framework 4.7 erfolgt die Serialisierung von Steuerzeichen durch <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> entsprechend dem Standard ECMAScript 6. Dieses Verhalten wird standardmäßig für Anwendungen aktiviert, die auf .NET Framework 4.7 ausgerichtet sind, und ist ein optionales Feature für Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, jedoch auf eine frühere Version von .NET Framework ausgerichtet sind. Weitere Informationen finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />

#### <a name="networking"></a>Netzwerk

.NET Framework 4.7 bietet nun die folgenden netzwerkbezogenen Features:

**Standardmäßig Betriebssystemunterstützung für TLS-Protokolle***

Der TLS-Stapel, der von <xref:System.Net.Security.SslStream?displayProperty=nameWithType> und vorgelagerten Komponenten im Stapel wie z.B. HTTP, FTP und SMTP verwendet wird, ermöglicht Entwicklern, die vom Betriebssystem unterstützten TLS-Standardprotokolle zu verwenden. Entwickler müssen eine TLS-Version nicht länger vordefinieren.

<a name="ASP-NET47" />

#### <a name="aspnet"></a>ASP.NET

In .NET Framework 4.7 bietet ASP.NET die folgenden neuen Features:

**Erweiterbarkeit des Objektcaches**

Ab .NET Framework 4.7 bietet ASP.NET eine neue Gruppe von APIs, die es Entwicklern ermöglichen, die ASP.NET- Standardimplementierungen für das Zwischenspeichern von Objekten im Arbeitsspeicher und dessen Überwachung zu ersetzen. Entwickler können jetzt die drei folgenden Komponenten ersetzen, wenn die ASP.NET-Implementierung nicht geeignet ist:

- **Objektcachespeicher**. Mithilfe des neuen Abschnitts für die Konfiguration von Cacheanbietern können Entwickler neue Implementierungen eines Objektcaches für eine ASP.NET-Anwendung einbinden, indem die neue **ICacheStoreProvider**-Schnittstelle verwendet wird.

- **Speicherüberwachung**. Der Standardspeichermonitor in ASP.NET benachrichtigt Anwendungen, sobald sie sich dem für den Prozess konfigurierten Grenzwert für private Bytes nähern oder der insgesamt verfügbare physische Arbeitsspeicher knapp wird. Bei Annäherung an diese Grenzwerte werden Benachrichtigungen ausgelöst. Bei einigen Anwendungen werden Benachrichtigungen erst ausgelöst, sobald die konfigurierten Grenzwerte schon fast erreicht sind, sodass keine sinnvolle Reaktion möglich ist. Entwickler können nun mithilfe der <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType>-Eigenschaft ihre eigene Arbeitsspeicherüberwachung schreiben, um die Standardeinstellung zu ersetzen.

- **Reaktionen bei Erreichen des Speichergrenzwerts**. Standardmäßig versucht ASP.NET, den Objektcache zu trimmen und regelmäßig <xref:System.GC.Collect%2A?displayProperty=nameWithType> aufzurufen, wenn der Prozessgrenzwert für private Bereiche fast erreicht ist. Für einige Anwendungen ist die Häufigkeit der Aufrufe von <xref:System.GC.Collect%2A?displayProperty=nameWithType> oder die Menge des Caches, der getrimmt wird, ineffizient. Entwickler können jetzt das Standardverhalten ersetzen oder ergänzen, indem für den Speichermonitor der Anwendung **IObserver**-Implementierungen abonniert werden.

<a name="wcf47" />

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

Windows Communication Foundation (WCF) bietet nun die folgenden Features und Änderungen:

**Möglichkeit zum Konfigurieren der Standardsicherheitseinstellungen für Nachrichten für TLS1.1.1 und TLS1.1.2**

Ab .NET Framework 4.7 ermöglicht WCF das Konfigurieren von TSL 1.1 oder TLS 1.2 zusätzlich zu SSL 3.0 und TLS 1.0 als Standardprotokoll für die Sicherheit von Nachrichten. Diese Einstellung ist optional. Um sie zu aktivieren, müssen Sie der Anwendungskonfigurationsdatei den folgenden Eintrag hinzufügen:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

**Verbesserte Zuverlässigkeit von WCF-Anwendungen und WCF-Serialisierung**

WCF umfasst eine Reihe von Codeänderungen zum Vermeiden von Racebedingungen, wodurch Leistung und Zuverlässigkeit von Serialisierungsoptionen verbessert werden. Dazu gehören:

- Bessere Unterstützung für das Kombinieren von asynchronem und synchronem Code in Aufrufen von **SocketConnection.BeginRead** und **SocketConnection.Read**.
- Verbesserte Zuverlässigkeit beim Abbrechen einer Verbindung mit **SharedConnectionListener** und **DuplexChannelBinder**.
- Verbesserte Zuverlässigkeit von Serialisierungsvorgängen beim Aufrufen der <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType>-Methode.
- Verbesserte Zuverlässigkeit beim Entfernen eines Waiters durch Aufrufen der **ChannelSynchronizer.RemoveWaiter**-Methode.

<a name="wf47" />

#### <a name="windows-forms"></a>Windows Forms

In .NET Framework 4.7 bietet Windows Forms eine bessere Unterstützung für Monitore mit hohem DPI-Wert.

**Unterstützung hoher DPI-Werte**

Beginnend mit auf .NET Framework 4.7 ausgerichteten Anwendungen unterstützt .NET Framework für Windows Forms-Anwendungen hohe und dynamische DPI-Werte. Durch die Unterstützung hoher DPI-Werte werden das Layout und die Darstellung von Formularen und Steuerelementen auf Monitoren mit hohen DPI-Einstellungen verbessert. Dynamische DPI-Werte ermöglichen das Ändern von Layout und Darstellung von Formularen und Steuerelementen, wenn der Benutzer die DPI-Einstellung oder den Skalierungsfaktor der Anzeige einer ausgeführten Anwendung ändert.

Die Unterstützung hoher DPI-Werte ist ein optionales Feature, das Sie durch Festlegen des Abschnitts [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) in der Anwendungskonfigurationsdatei konfigurieren können. Weitere Informationen zum Hinzufügen der Unterstützung hoher und dynamischer DPI-Werte zu Ihrer Windows Forms-Anwendung finden Sie unter [Unterstützung hoher DPI-Werte in Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47" />

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.7 gibt es für WPF die folgenden Verbesserungen:

**Unterstützung für Touch-/Tablettstiftstapel basierend auf Windows-WM_POINTER-Nachrichten**

Sie haben nun die Möglichkeit, einen auf [-Windows-Nachrichten](https://docs.microsoft.com/previous-versions/windows/desktop/InputMsg/messages) basierenden Touch-/Tablettstiftstapel anstelle der Windows Ink Services Plattform (WISP) zu verwenden. Dies ist ein optionales Feature in .NET Framework. Weitere Informationen finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

**Neue Implementierung für Druck-APIs von WPF**

Die Druck-APIs von WPF in der <xref:System.Printing.PrintQueue?displayProperty=nameWithType>-Klasse rufen die Windows-API [PrintDocumentPackage](/windows/desktop/printdocs/tailored-app-printing-api) anstelle der veralteten [XPS-Druck-API](/windows/desktop/printdocs/xps-printing) auf. Die Auswirkung dieser Änderung auf die Anwendungskompatibilität finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="v462" />

## <a name="whats-new-in-net-framework-462"></a>Neuerungen in .NET Framework 4.6.2

.NET Framework 4.6.2 umfasst neue Features in den folgenden Bereichen:

- [ASP.NET](#ASPNET462)

- [Zeichenkategorien](#Strings)

- [Kryptografie](#Crypto462)

- [SQLClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#clickonce-1)

- [Konvertieren von Windows Forms und WPF-Apps in UWP-Apps](#UWPConvert)

- [Verbesserungen beim Debugging](#Debug462)

Eine Liste der neuen APIs, die .NET Framework 4.6.2 hinzugefügt wurden, finden Sie unter [API-Änderungen für .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) auf GitHub. Eine Liste der Verbesserungen von Features und Fehlerkorrekturen in .NET Framework 4.6.2 finden Sie unter [Liste mit Änderungen für .NET Framework 4.6.2](https://go.microsoft.com/fwlink/?LinkId=708778) auf GitHub.  Weitere Informationen finden Sie unter [Ankündigung von .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/) im .NET-Blog.

<a name="ASPNET462" />

### <a name="aspnet"></a>ASP.NET

In .NET Framework 4.6.2 bietet ASP.NET die folgenden Verbesserungen:

**Verbesserte Unterstützung lokalisierter Fehlermeldungen in Validierungssteuerelementen für Datenanmerkungen**

Mit Validierungssteuerelementen für Datenanmerkungen können Sie eine Überprüfung durchführen, indem Sie mindestens ein Attribut einer Klasseneigenschaft hinzufügen. Das Element <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> des Attributs definiert den Text der Fehlermeldung, falls die Überprüfung fehlschlägt. Ab .NET Framework 4.6.2 ist es einfach, mit ASP.NET Fehlermeldungen zu lokalisieren. Fehlermeldungen werden lokalisiert, wenn:

1. <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> im Validierungsattribut vorhanden ist.

2. die Ressourcendatei im Ordner „App_LocalResources“ gespeichert ist.

3. Der Name der lokalisierten Ressourcendatei ist folgendermaßen aufgebaut: `DataAnnotation.Localization.{`*Name*`}.resx`, wobei *Name* einen Kulturnamen im Format *Sprachcode*`-`*Länder-/Regionscode* oder *Sprachcode* darstellt.

4. Der Schlüsselname der Ressource ist die Zeichenfolge, die dem Attribut <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> zugewiesen ist, und deren Wert ist die lokalisierte Fehlermeldung.

Das folgende Datenanmerkungsattribut definiert z. B. die Fehlermeldung der Standardkultur für eine ungültige Bewertung.

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

Sie können dann eine Ressourcendatei erstellen, DataAnnotation.Localization.fr.resx, deren Schlüssel die Zeichenfolge der Fehlermeldung und ihr Wert die lokalisierte Fehlermeldung ist. Die Datei muss sich im Ordner `App.LocalResources` befinden. Das folgende Beispiel enthält den Schlüssel und seinen Wert in einer lokalisierten Fehlermeldung (Französisch, fr):

| name                                 | Wert                                     |
| ------------------------------------ | ----------------------------------------- |
| Die Bewertung muss zwischen 1 und 10 liegen. | La note doit être comprise entre 1 et 10. |

 Darüber hinaus ist die Lokalisierung der Datenanmerkung erweiterbar. Entwickler können ihren eigenen Anbieter für die zu lokalisierenden Zeichenfolgen in einer Ressourcendatei verwenden, indem Sie die <xref:System.Web.Globalization.IStringLocalizerProvider>-Schnittstelle implementieren, um Lokalisierungszeichenfolgen an einem anderen Speicherort zu speichern, jedoch nicht in einer Ressourcendatei.

 **Async-Unterstützung für Sitzungszustands-Schlüsselspeicheranbieter**

 ASP.NET erlaubt nun, dass Methoden, die eine Aufgabe zurückgeben, zusammen mit dem Anbieter für die Speicherung von Daten aus der Variable „Sitzungszustand“ verwendet werden können. Dadurch stehen ASP .NET-Apps die Vorteile zur Verfügung, die async in Sachen Skalierbarkeit bietet. Für die Unterstützung asynchroner Operationen bei Anbietern für die Speicherung von Daten aus der Variable „Sitzungszustand“, enthält ASP.NET eine neue Schnittstelle namens <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>. Diese Schnittstelle erbt von <xref:System.Web.IHttpModule> und erlaubt Entwicklern, ihr eigenes Sitzungszustandsmodul und Anbieter für die Speicherung von async-Sitzungen zu implementieren. Die Schnittstelle wird wie folgt definiert:

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

```vb
Public Interface ISessionStateModule : Inherits IHttpModule
   Sub ReleaseSessionState(context As HttpContext)
   Function ReleaseSessionStateAsync(context As HttpContext) As Task
End Interface
```

 Zusätzlich enthält die <xref:System.Web.SessionState.SessionStateUtility>-Klasse zwei neue Methoden, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> und <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, die verwendet werden können, um asynchrone Vorgänge zu unterstützen.

 **Async-Unterstützung für Ausgabecacheanbieter**

 Ab .NET Framework 4.6.2 können Methoden, die Tasks zurückgeben, mit Ausgabecacheanbietern verwendet werden, um die Vorteile der Skalierbarkeit der Asynchronität zu bieten.  Anbieter, die diese Methoden bereitstellen, verringern die Anzahl blockierter Threads auf einem Webserver und verbessern die Skalierbarkeit eines ASP.NET-Diensts.

 Die folgenden APIs wurden hinzugefügt, um asynchrone Ausgabecacheanbieter zu unterstützen:

- Die <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType>-Klasse, die von <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> erbt und es Entwicklern ermöglicht, einen asynchronen Ausgabecacheanbieter zu implementieren.

- Die <xref:System.Web.Caching.OutputCacheUtility>-Klasse, die Hilfsmethoden zum Konfigurieren des Ausgabecaches bereitstellt.

- 18 neue Methoden in der <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType>-Klasse. Diese sind <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> und <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 neue Methoden in der <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType>-Klasse: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> und <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 neue Methoden in der <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType>-Klasse: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> und <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 neue Methoden in der <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType>-Klasse: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> und <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- In der <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType>-Klasse, die Methode <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>.

- In der <xref:System.Web.Caching.CacheDependency>-Klasse, die Methode <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>.

<a name="Strings" />

### <a name="character-categories"></a>Zeichenkategorien

Zeichen in .NET Framework 4.6.2 werden auf Grundlage des [Unicode-Standards, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) klassifiziert. In .NET Framework 4.6 und .NET Framework 4.6.1 werden Zeichen basierend auf den Zeichenkategorien von Unicode 6.3 klassifiziert.

Die Unterstützung von Unicode 8.0 ist beschränkt auf die Klassifizierung von Zeichen durch die <xref:System.Globalization.CharUnicodeInfo>-Klasse und auf Typen und Methoden, die darauf basieren. Dazu gehören die <xref:System.Globalization.StringInfo>-Klasse, die überladene <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType>-Methode, und die [Zeichenklassen](../../standard/base-types/character-classes-in-regular-expressions.md), die von der .NET Framework-Engine für reguläre Ausdrücke erkannt werden.  Der Vergleich und die Sortierung von Zeichen und Zeichenfolgen sind von dieser Änderung nicht betroffen und beruhen weiterhin auf dem zugrunde liegenden Betriebssystem oder auf Windows 7-Systemen auf Zeichendaten, die vom .NET Framework bereitgestellt wurden.

Änderungen in Zeichenkategorien von Unicode 6.0 bis 7.0 Unicode finden Sie unter [Unicode Standard, Version 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) auf der Website des Unicode-Konsortiums. Änderungen von Unicode 7.0 bis 8.0 Unicode finden Sie unter [Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) auf der Website des Unicode-Konsortiums.

<a name="Crypto462" />

### <a name="cryptography"></a>Kryptografie

**Unterstützung von X 509-Zertifikaten, die FIPS 186-3 DSA enthalten**

.NET Framework 4.6.2 unterstützt DSA X509-Zertifikate (Digital Signature Algorithm), deren Schlüssel den FIPS 186-2-Grenzwert von 1024 Bits überschreiten.

Zusätzlich zur Unterstützung der höheren Schlüsselgrößen von FIPS 186-3 erlaubt .NET Framework 4.6.2 die Berechnung von Signaturen mit der SHA-2-Familie von Hashalgorithmen (SHA256, SHA384 und SHA512). Die Unterstützung von FIPS 186-3 wird durch die neue <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType>-Klasse bereitgestellt.

Gemäß der aktuellen Änderungen an der <xref:System.Security.Cryptography.RSA>-Klasse im .NET Framework 4.6 und an der <xref:System.Security.Cryptography.ECDsa>-Klasse im .NET Framework 4.6.1 verfügt die abstrakte Basisklasse <xref:System.Security.Cryptography.DSA> im .NET Framework 4.6.2 über zusätzliche Methoden, um Aufrufern die Verwendung dieser Funktion ohne die Umwandlung zu gestatten. Sie können die Erweiterungsmethode <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> verwenden, um Daten zu signieren, so wie in folgendem Beispiel dargestellt.

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

Sie können auch die Erweiterungsmethode <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> aufrufen, um signierte Daten zu überprüfen, so wie in folgendem Beispiel dargestellt.

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

**Verbesserte Übersichtlichkeit für Eingaben in die Schlüsselableitungsfunktions-Routinen für den Diffie-Hellman-Schlüsselaustausch**

In.NET Framework 3.5 wurde die Unterstützung der Elliptic Curve Diffie-Hellman-Schlüsselvereinbarung mit drei verschiedenen Routinen für die Schlüsselableitungsfunktion (KDF) hinzugefügt. Die Eingaben in die Routinen und auch die Routinen selbst wurden mithilfe von Eigenschaften auf dem <xref:System.Security.Cryptography.ECDiffieHellmanCng>-Objekt konfiguriert. Da jedoch nicht jede Routine jede input-Eigenschaft liest,sorgte dies bisher bei Entwicklern für reichlich Verwirrungspotenzial.

Dieses Problem wurde in .NET Framework 4.6.2 behoben, indem die folgenden drei Methoden zur <xref:System.Security.Cryptography.ECDiffieHellman>-Basisklasse hinzugefügt wurden, sodass diese KDF-Routinen und deren Eingaben eindeutiger dargestellt werden:

|Die ECDiffieHellman-Methode|BESCHREIBUNG|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> wobei *x* das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus ist.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> wobei *x* das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus ist.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mit dem Ableitungsalgorithmus der TLS-Pseudozufallsfunktion (pseudo-random function; PRF) ab.|

**Unterstützung der symmetrischen Verschlüsselung persistenter Schlüssel**

Die Windows-Kryptografiebibliothek (CNG) unterstützt nun die Speicherung persistenter symmetrischer Schlüssel und die Verwendung von auf der Hardware gespeicherten symmetrischen Schlüsseln. Durch .NET Framework 4.6.2 können Entwickler dieses Feature jetzt nutzen.  Da das Konzept des Schlüsselnamens und des Schlüsselanbieters implementierungsspezifisch ist, erfordert die Nutzung dieser Funktion die Verwendung des Konstruktors der konkreten Implementierungstypen anstatt der bevorzugten Herangehensweise des Unternehmens (z.B. durch aufrufen von `Aes.Create`).

Die Unterstützung der symmetrischen Verschlüsselung persistenter Schlüssel ist für die Algorithmen AES (<xref:System.Security.Cryptography.AesCng>) und 3DES (<xref:System.Security.Cryptography.TripleDESCng>) verfügbar. Beispiel:

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

**SignedXml-Unterstützung des Hashing von SHA-2**

.NET Framework 4.6.2 unterstützt nun die Klasse <xref:System.Security.Cryptography.Xml.SignedXml> für die Signaturmethoden RSA-SHA256, RSA-SHA384 und RSA-SHA512 PKCS#1 und für die Referenzdigestalgorithmen SHA256, SHA384 und SHA512.

Die URI-Konstanten werden alle für <xref:System.Security.Cryptography.Xml.SignedXml> verfügbar gemacht:

|SignedXml-Feld|Konstante|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 Alle Programme, die einen benutzerdefinierten <xref:System.Security.Cryptography.SignatureDescription>-Handler in <xref:System.Security.Cryptography.CryptoConfig> registriert haben, um Unterstützung für diese Algorithmen hinzuzufügen, funktionieren weiterhin wie gewohnt. Da nun jedoch Plattformstandards existieren, ist die <xref:System.Security.Cryptography.CryptoConfig>-Registrierung nicht mehr notwendig.

<a name="SQLClient" />

### <a name="sqlclient"></a>SqlClient

Der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) bietet die folgenden neuen Features im .NET Framework 4.6.2:

**Verbindungspooling und Timeouts mit Azure SQL-Datenbanken**

Wenn das Verbindungspooling aktiviert ist und ein Timeoutfehler oder ein anderer Anmeldefehler auftritt, wird eine Ausnahme zwischengespeichert sowie die zwischengespeicherte Ausnahme wird für jeden nachfolgenden Verbindungsversuch für die nächsten 5 Sekunden bis zu einer Minute.  Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).

Dieses Verhalten ist bei einer Verbindung zu Azure SQL-Datenbanken unerwünscht, da Verbindungsversuche mit flüchtigen Fehlern fehlschlagen können, die normalerweise schnell wiederhergestellt werden. Das Sperrfristverhalten des Verbindungspools wird entfernt, wenn die Verbindungsversuche zu Azure SQL-Datenbanken fehlschlagen, damit erneute Verbindungsversuche leichter erfolgen können.

Mit dem Hinzufügen des neuen `PoolBlockingPeriod`-Schlüsselworts können Sie die Sperrfrist auswählen, die für Ihre App am besten geeignet ist. Mögliche Werte:

<xref:System.Data.SqlClient.PoolBlockingPeriod.Auto>

Die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einer Azure SQL-Datenbank herstellt, ist deaktiviert, und die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einem anderen SQL-Server herstellt, ist aktiviert. Dies ist der Standardwert. Wenn der Serverendpunktname eine der folgenden Endungen besitzt, werden sie als Azure SQL-Datenbanken bezeichnet:

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

<xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>

Die Sperrfrist des Verbindungspools ist immer aktiviert.

<xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock>

Die Sperrfrist des Verbindungspools ist immer deaktiviert.

**Verbesserungen für Always Encrypted**

SQLClient führt zwei Verbesserungen für Always Encrypted ein:

- Verschlüsselungsmetadaten für Abfrageparameter werden nun zwischengespeichert, um die Leistung von parametrisierten Abfragen von verschlüsselten Datenbankspalten zu verbessert. Wenn die Eigenschaft <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> auf `true` festgelegt ist (was der Standardeinstellung entspricht) und dieselbe Abfrage mehrmals ausgeführt wird, ruft der Client die Parametermetadaten nur einmal vom Server ab.

- Spaltenverschlüsselungsschlüssel-Einträge im Schlüsselcache werden nun nach einem konfigurierbaren Zeitintervall entfernt, das mithilfe der <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType>-Eigenschaft festgelegt wird.

<a name="WCF" />

### <a name="windows-communication-foundation"></a>Windows Communication Foundation

In .NET Framework 4.6.2 wurde Windows Communication Foundation in den folgenden Bereichen erweitert:

**Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden**

Die WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe der Windows-Kryptografiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist in .NET Framework 4.6.2 auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn eine Anwendung auf .NET Framework 4.6.2 ausgerichtet ist, ist dieses Feature standardmäßig aktiviert.

Für Anwendungen, die auf das .NET Framework 4.6.1 und früher ausgerichtet sind, aber im .NET Framework 4.6.2 ausgeführt werden, kann dieses Feature aktiviert werden, indem die folgende Zeile dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Datei „app.config“ oder „web.config“ hinzugefügt wird.

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

**Bessere Unterstützung mehrerer Anpassungsregeln für die Sommerzeit durch die DataContractJsonSerializer-Klasse**

Kunden können eine Anwendungskonfigurationseinstellung verwenden, um zu bestimmen, ob die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>-Klasse mehrere Anpassungsregeln für eine Zeitzone unterstützt. Dies ist ein Opt-in-Feature. Fügen Sie die folgende Einstellung der Datei app.config hinzu, um sie zu aktivieren:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Wenn diese Funktion aktiviert ist, verwendet ein <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>-Objekt den <xref:System.TimeZoneInfo>-Typ anstelle des <xref:System.TimeZone>-Typs, um Datums-und Uhrzeitdaten zu deserialisieren. <xref:System.TimeZoneInfo> unterstützt mehrere Anpassungsregeln, die es ermöglichen, mit veralteten Zeitzonendaten. <xref:System.TimeZone> unterstützt dies nicht.

Weitere Informationen zur <xref:System.TimeZoneInfo>-Struktur und zu Zeitzonenanpassungen finden Sie unter [Übersicht über Zeitzonen](../../standard/datetime/time-zone-overview.md).

**NetNamedPipeBinding höchste Übereinstimmung**

WCF bietet eine neue App-Einstellung, die für Clientanwendungen festgelegt werden kann, um sicherzustellen, dass diese immer eine Verbindung zu dem Dienst herstellen, der an dem URI lauscht, der die höchste Übereinstimmung zu dem aufweist, den die Anwendungen anfordern. Wenn diese App-Einstellung auf `false` (Standard) festgelegt ist, ist es für Clients möglich, <xref:System.ServiceModel.NetNamedPipeBinding> zu verwenden, um zu versuchen, eine Verbindung zu einem Dienst herzustellen, der an einen URI lauscht, der eine Teilzeichenfolge des angeforderten URI darstellt.

Angenommen, ein Client versucht, eine Verbindung zu einem Dienst herzustellen, der an `net.pipe://localhost/Service1` lauscht, aber ein anderer Dienst auf dem Computer, der mit Administratorrechten ausgeführt wird, lauscht an `net.pipe://localhost`. Der Client würde versuchen, mit dieser App-Einstellung, die auf `false` festgelegt ist, eine Verbindung zu dem falschen Dienst herzustellen. Nach dem Festlegen der App-Einstellung auf `true`, wird der Client stets eine Verbindung zu den passendsten Dienst herstellen.

> [!NOTE]
> Clients, die <xref:System.ServiceModel.NetNamedPipeBinding> verwenden, suchen Dienste, die auf der Basisadresse des Diensts basieren (soweit vorhanden) anstatt die vollständige Endpunktadresse. Damit diese Einstellung immer funktioniert muss der Dienst eine eindeutige Basisadresse verwenden.

Fügen Sie die folgende App-Einstellung der App.config- oder Web.config-Datei der Anwendung Ihres Clients hinzu, um die Änderung zu aktivieren:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

**SSL 3.0 ist kein Standardprotokoll**

Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird SSL 3.0 nicht länger als eines der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet. In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 in der Protokollliste für NetTcp enthalten ist. Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln. Wenn Ssl3 erforderlich ist, verwenden Sie eine der folgenden Konfigurationsmechanismen, um es der Liste der ausgehandelten Protokolle hinzuzufügen.

- Die <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType>-Eigenschaft.

- Die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>-Eigenschaft.

- Der Abschnitt [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) des Abschnitts [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)

- Der Abschnitt [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) des Abschnitts [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md)

<a name="WPF462" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.6.2 wurde Windows Presentation Foundation in den folgenden Bereichen erweitert:

**Sortieren von Gruppen**

Eine Anwendung, die ein <xref:System.Windows.Data.CollectionView>-Objekt zum gruppieren von Daten verwenden, kann nun explizit deklarieren, wie die Gruppen sortiert werden. Das explizite Sortieren behebt das Problem der nicht-intuitiven Sortierung beim dynamischen Hinzufügen oder Entfernen von Gruppen und beim Ändern des Wert der beim Gruppieren beteiligten Elementeigenschaften durch eine App. Diese Vorgehensweise kann auch die Leistung des Gruppenerstellungsprozesses verbessern, indem Vergleiche der Gruppierungseigenschaften nicht bei der Sortierung der vollständigen Sammlung, sondern bei der Sortierung der Gruppen erfolgen/vorgenommen werden.

Zur Unterstützung der Gruppensortierung beschreiben die neuen <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType>- und <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType>-Eigenschaften wie die Sammlung der Gruppen sortiert wird, die vom <xref:System.ComponentModel.GroupDescription>-Objekt erstellt wurden. Dies ist vergleichbar mit der Art wie gleichnamigen <xref:System.Windows.Data.ListCollectionView>-Eigenschaften die Sortierung der Datenelemente beschreiben.

In den häufigsten Fällen können zwei neue statistische Eigenschaften der <xref:System.Windows.Data.PropertyGroupDescription>-Klasse verwendet werden, nämlich <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> und <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>.

Zum Beispiel gruppiert der folgende XAML-Code Daten nach Alter, sortiert die Gruppen in aufsteigender Reihenfolge und gruppierten die Elemente in den einzelnen Gruppen anhand des Nachnamens.

```xaml
<GroupDescriptions>
     <PropertyGroupDescription
         PropertyName="Age"
         CustomSort=
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

**Bildschirmtastatur-Unterstützung**

Die Bildschirmtastatur-Unterstützung ermöglicht die fokussierte Verfolgung in WPF-Anwendungen, indem automatisch die neue Bildschirmtastatur in Windows 10 aufgerufen und geschlossen wird, wenn die Fingereingabe von einem Steuerelement empfangen wird, das Texteingabe nutzen kann.

In früheren Versionen des .NET-Frameworks konnte für WPF-Anwendungen die Fokusverfolgung nur aktiviert werden, wenn in WPF die Unterstützung für Stifte und Touchgesten deaktiviert wurde.  Die WPF-Anwendungen müssen daher zwischen der vollständiger WPF-Gestenunterstützung und der Windows-Mausheraufstufung wählen.

**DPI pro Monitor**

Um die zunehmende Verbreitung hoher und hybrider DPI-Umgebungen für WPF-Apps zu unterstützen, sorgt WPF dafür, dass monitorspezifische DPI-Werte in .NET Framework 4.6.2 erkannt werden. Weitere Informationen dazu, wie Sie in Ihrer WPF-Anwendung dafür sorgen, dass Sie mit monitorspezifischen DPI-Werten kompatibel ist, finden Sie unter [Samples and Developer Guide](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) (Beispiele und Entwicklerhandbuch) auf GitHub.

In früheren Versionen von .NET Framework sind WPF-Apps kompatibel mit systemspezifischen DPI-Werten. Die Benutzeroberfläche der Anwendung wird anders gesagt ggf. mit dem Betriebssystem skaliert, abhängig von der DPI des Monitors, auf dem die App gerendert wird.

Für Apps, die unter .NET Framework 4.6.2 ausgeführt werden, können Sie monitorspezifische DPI-Änderungen in WPF-Apps deaktivieren, indem Sie eine Konfigurationsanweisung zum Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen (siehe das folgende Beispiel):

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462" />

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

In .NET Framework 4.6.2 wurde Windows Workflow Foundation im folgenden Bereich erweitert:

**Unterstützung für C#-Ausdrücke und IntelliSense im neu gehosteten WF-Designer**

Ab .NET Framework 4.5 unterstützt Workflow Foundation C#-Ausdrücke sowohl im Visual Studio-Designer als auch in Codeworkflows. Der neu gehostete Workflow-Designer ist eine wichtige Funktion von WF, die zulässt, dass sich der Workflow-Designer in einer Anwendung außerhalb von Visual Studio befindet (z.B. in WPF).  Windows Workflow Foundation bietet die Möglichkeit der Unterstützung von C#-Ausdrücken und IntelliSense im neu gehosteten Workflow-Designer. Weitere Informationen finden Sie im [Windows Workflow Foundation-Blog](https://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).

`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` In Versionen des .NET Framework vor .NET Framework 4.6.2 wird IntelliSense im WF-Designer unterbrochen, wenn ein Kunde ein Workflowprojekt in Visual Studio neu erstellt. Obwohl die Erstellung des Projekts erfolgreich war, können die Workflowtypen nicht im Designer gefunden werden und IntelliSense gibt Warnungen für die fehlenden Workflowtypen im Fenster **Fehlerliste** aus. .NET Framework 4.6.2 behebt dieses Problem und macht IntelliSense verfügbar.

**Workflow V1-Anwendungen mit aktivierter Workflowüberwachung werden im FIPS-Modus ausgeführt**

Computer mit aktiviertem FIPS-Kompatibilitätsmodus können jetzt erfolgreich eine Anwendung, die dem Stil der Workflowversion 1 entspricht, mit aktivierter Workflowüberwachung ausführen. Sie müssen die folgenden Änderungen in Ihrer app.config-Datei vornehmen, um dieses Szenario zu aktivieren:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

Wenn dieses Szenario nicht aktiviert ist, führt das Ausführen der Anwendung weiterhin dazu, dass eine Ausnahme mit folgender Meldung ausgelöst wird: „Diese Implementation ist nicht Teil der Windows Platform FIPS-überprüften kryptografischen Algorithmen.“

**Verbesserungen des Workflows bei der Verwendung von dynamischen Updates mit dem Workflow-Designer von Visual Studio**

Der Workflow-Designer, der Flussdiagramm-Aktivitätsdesigner und andere Workflow-Aktivitätsdesigner laden nun erfolgreich Workflows, die nach dem Aufruf der <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>-Methode gespeichert wurden und zeigen diese an. In Versionen des .NET Framework vor .NET Framework 4.6.2 kann das Laden einer XAML-Datei in Visual Studio für einen Workflow, der nach dem Aufruf von <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> gespeichert wurde, zu folgenden Problemen führen:

- Der Workflow-Designer kann die XAML-Datei nicht ordnungsgemäß laden (wenn sich die <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> am Ende der Zeile befindet).

- Der Flussdiagramm-Aktivitätsdesigner oder andere Workflow-Aktivitätsdesigner können möglicherweise alle Objekte an ihrem Standardspeicherort anzeigen, im Gegensatz zu angefügten Eigenschaftswerten.

<a name="clickonce-1" />

### <a name="clickonce"></a>ClickOnce

ClickOnce wurde zur Unterstützung von TLS 1.1 und TLS 1.2 neben dem 1.0-Protokoll aktualisiert, das schon unterstützt wird. ClickOnce erkennt automatisch, welches Protokoll erforderlich ist. Es sind keine zusätzlichen Schritte innerhalb der ClickOnce-Anwendung erforderlich, um die TLS 1.1 und 1.2-Unterstützung zu aktivieren.

<a name="UWPConvert" />

### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Konvertieren von Windows Forms und WPF-Apps in UWP-Apps

Windows bietet nun Möglichkeiten, vorhandene Windows Desktop-Apps, einschließlich WPF- und Windows Forms-Apps, auf der Universal Windows Platform (UWP) bereitzustellen. Diese Technologie agiert als Brücke, indem sie Ihnen ermöglicht, Ihre vorhandene Codebasis nach und nach zu UWP zu migrieren und so Ihre App auf allen Windows 10-Geräten bereitzustellen.

Konvertierte Desktop-Apps erlangen eine App-Identität ähnlich der App-Identität von UWP-Apps, wodurch UWP-APIs zugänglich gemacht werden, um Funktionen wie Live-Kacheln und Benachrichtigungen zu aktivieren. Die App verhält sich weiterhin wie zuvor und wird als voll vertrauenswürdige App ausgeführt. Sobald die App konvertiert ist, kann ein App-Container-Prozess zum vorhandenen voll vertrauenswürdigen Prozess hinzugefügt werden, um eine adaptive Benutzeroberfläche hinzuzufügen. Wenn alle Funktionen in den App-Container-Prozess verschoben werden, kann der vollständig vertrauenswürdige Prozess entfernt werden, und die neue UWP-App kann auf allen Windows 10-Geräten zur Verfügung gestellt werden.

<a name="Debug462" />

### <a name="debugging-improvements"></a>Verbesserungen beim Debugging

Die *nicht verwaltete Debug-API* wurde im .NET Framework 4.6.2 verbessert, um zusätzlichen Analysen durchzuführen, wenn <xref:System.NullReferenceException> ausgelöst wird. Somit ist es möglich, zu bestimmen, welche Variable in einer einzelnen Zeile des Quellcodes `null` ist.   Um dieses Szenario zu unterstützen, wurden die folgenden APIs der nicht verwalteten Debug-API hinzugefügt.

- Die Schnittstellen [ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md), und [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), die den Ursprungsort verwalteter Variablen verfügbar machen. Dadurch können Debugger Codeflussanalysen durchführen, wenn eine <xref:System.NullReferenceException>-Klasse auftritt und auf dieser Grundlage die verwaltete Variable zu bestimmen, die dem nativen Speicherort entspricht, der `null` war.

- Die Methode [ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) bietet eine Zuordnung für die Schnittstelle „ICorDebugType“ zur Struktur [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md), wodurch der Debugger eine [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md)-Struktur ohne eine Instanz der Schnittstelle „ICorDebugType“ abrufen kann. Vorhandenen APIs auf der [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md)-Struktur kann dann verwendet werden, um das Klassenlayout des Typs zu bestimmen.

<a name="v461" />

## <a name="whats-new-in-net-framework-461"></a>Neuerungen in .NET Framework 4.6.1

.NET Framework 4.6.1 umfasst neue Features in den folgenden Bereichen:

- [Kryptografie](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Profilerstellung](#Profile461)

- [NGen](#NGEN461)

Weitere Einzelheiten zu .NET Framework 4.6.1 finden Sie in den folgenden Themen:

- [Liste der Änderungen in .NET Framework 4.6.1](https://go.microsoft.com/fwlink/?LinkId=622964)

- [Anwendungskompatibilität in 4.6.1](../migration-guide/application-compatibility.md)

- [Unterschiede der .NET Framework-API](https://go.microsoft.com/fwlink/?LinkId=622989) (auf GitHub)

<a name="Crypto" />

### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Kryptografie: Unterstützung für X 509-Zertifikate mit ECDSA

RSACng-Unterstützung für X509-Zertifikate in .NET Framework 4.6. .NET Framework 4.6.1 fügt Unterstützung für ECDSA (Elliptic Curve Digital Signature Algorithm) X509-Zertifikate hinzu.

ECDSA bietet eine bessere Leistung und einen sichereren Kryptografiealgorithmus als RSA. Somit ist die Lösung eine hervorragende Wahl, wenn es um TLS (Transport Layer Security)-Leistung und Skalierbarkeit geht. Die .NET Framework-Implementierung schließt Aufrufe in die vorhandene Windows-Funktionalität ein.

Im folgenden Codebeispiel wird gezeigt, wie einfach es ist, eine Signatur für einen Bytedatenstrom mit der neuen in .NET Framework 4.6.1 enthaltenen ECDSA-Unterstützung für X509-Zertifikate zu generieren.

[!code-csharp[whatsnew.461.crypto#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
[!code-vb[whatsnew.461.crypto#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

Dies steht in deutlichem Gegensatz zum Code, der zum Generieren einer Signatur in .NET Framework 4.6 erforderlich war.

[!code-csharp[whatsnew.461.crypto#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
[!code-vb[whatsnew.461.crypto#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461" />

### <a name="adonet"></a>ADO.NET

ADO.NET wurde um die folgenden Features erweitert:

**Always Encrypted-Unterstützung für hardwaregeschützte Schlüssel**

ADO.NET unterstützt jetzt die systemeigene Speicherung von "Always Encrypted"-Spaltenhauptschlüsseln in Hardwaresicherheitsmodulen (Hardware Security Modules, HSMs). Mit dieser Unterstützung profitieren Kunden von asymmetrischen, in HSMs gespeicherten Schlüsseln, ohne benutzerdefinierte Spaltenhauptschlüssel-Speicheranbieter zu schreiben und in Anwendungen registrieren zu müssen.

Kunden müssen die vom HSM-Anbieter bereitgestellten CSP-Anbieter oder CNG-Schlüsselspeicheranbieter auf den App-Servern oder Clientcomputern installieren, um über die in einem HSM gespeicherten Spaltenhauptschlüssel auf die mit "Always Encrypted" geschützten Daten zuzugreifen.

**Verbessertes <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>-Verbindungsverhalten für AlwaysOn**

SqlClient ermöglicht jetzt automatisch schnellere Verbindungen mit einer AlwaysOn-Verfügbarkeitsgruppe (Availability Group, AG). Er erkennt auf transparente Weise, ob die Anwendung eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe in einem anderen Subnetz herstellt, ermittelt schnell den aktiven Server und stellt eine Verbindung mit dem Server her. Vor dieser Version musste eine Anwendung `"MultisubnetFailover=true"` in die Verbindungszeichenfolge einschließen, um anzugeben, dass eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe hergestellt wurde. Wenn das Verbindungsschlüsselwort nicht auf `true` festgelegt wird, kann bei der Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe ein Anwendungstimeout auftreten. Bei dieser Version muss eine Anwendung <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> *nicht* mehr auf `true` festlegen. Weitere Informationen zur SqlClient-Unterstützung für AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

Windows Presentation Foundation umfasst eine Reihe von Verbesserungen und Änderungen.

**Verbesserte Leistung**

Die Verzögerung beim Auslösen von Touchereignissen wurde in .NET Framework 4.6.1 behoben. Wenn eine Eingabe in ein <xref:System.Windows.Controls.RichTextBox>-Steuerelement erfolgt, wird außerdem der Renderthread während der schnellen Eingabe nicht mehr vollständig beansprucht.

**Verbesserte Rechtschreibprüfung**

Die Rechtschreibprüfung in WPF wurde unter Windows 8.1 und höheren Versionen aktualisiert, um die Betriebssystemunterstützung für die Rechtschreibprüfung zusätzlicher Sprachen zu nutzen.  Bezüglich der Funktionalität in Windows-Versionen vor Windows 8.1 gibt es keine Änderung.

Wie in früheren .NET Framework-Versionen wird die Sprache eines <xref:System.Windows.Controls.TextBox>-Steuerelements oder <xref:System.Windows.Controls.RichTextBox>-Blocks ermittelt, indem in der folgenden Reihenfolge nach Informationen gesucht wird:

- `xml:lang`, falls vorhanden.

- Aktuelle Eingabesprache

- Aktuelle Threadkultur

Weitere Informationen zur Sprachunterstützung in WPF finden Sie im [WPF-Blogbeitrag zu .NET Framework 4.6.1-Features](https://go.microsoft.com/fwlink/?LinkID=691819).

**Zusätzliche Unterstützung für benutzerdefinierte Wörterbücher pro Benutzer**

In .NET Framework 4.6.1 erkennt WPF benutzerdefinierte Wörterbücher, die global registriert sind. Diese Funktion ist zusätzlich zur Registrierung der Wörterbücher pro Steuerelement verfügbar.

In früheren WPF-Versionen wurden Listen ausgeschlossener Wörter und AutoKorrektur-Listen von benutzerdefinierten Wörterbüchern nicht erkannt. Diese werden unter Windows 8.1 und Windows 10 mittels Dateien unterstützt, die im Verzeichnis `%AppData%\Microsoft\Spelling\<language tag>` abgelegt werden können.  Für diese Dateien gelten die folgenden Regeln:

- Die Dateien sollten über die Erweiterungen ".dic" (hinzugefügte Wörter), ".exc" (ausgeschlossene Wörter) oder ".acl" (AutoKorrektur-Wörter) verfügen.

- Außerdem sollten sie das UTF-16LE-Nur-Text-Format aufweisen, das mit der Bytereihenfolgenmarke (Byte Order Mark, BOM) beginnt.

- Jede Zeile sollte aus einem Wort (aus der Liste hinzugefügter und ausgeschlossener Wörter) oder einem AutoKorrektur-Paar bestehen, bei dem die Wörter durch einen senkrechten Strich ("&#124;") (in der AutoKorrektur-Wortliste) getrennt sind.

- Diese Dateien sind schreibgeschützt und werden vom System nicht geändert.

> [!NOTE]
> Diese neuen Dateiformate werden von den WPF-Rechtschreibprüfungs-APIs nicht direkt unterstützt, sodass die benutzerdefinierten Wörterbücher, die in Anwendungen für WPF bereitgestellt werden, weiterhin LEX-Dateien verwenden sollten.

**Beispiele**

Sie finden mehrere WPF-Beispiele im GitHub-Repository unter [Microsoft/WPF-Samples](https://github.com/Microsoft/WPF-Samples). Helfen Sie uns bei der Verbesserung unserer Beispiele, indem Sie uns einen Pull Request senden oder ein [GitHub-Problem](https://github.com/Microsoft/WPF-Samples/issues) eröffnen.

**DirectX-Erweiterungen**

WPF enthält ein [NuGet-Paket](https://go.microsoft.com/fwlink/?LinkID=691342) mit neuen Implementierungen von <xref:System.Windows.Interop.D3DImage>. Diese erleichtern die Interoperabilität mit DX10- und Dx11-Inhalten. Der Code für dieses Paket steht als Open Source-Code auf [GitHub](https://github.com/Microsoft/WPFDXInterop) zur Verfügung.

<a name="WWF461" />

### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Transaktionen

Von der <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType>-Methode kann jetzt ein anderer Manager für verteilte Aktionen als MSDTC verwendet werden, um die Transaktion höherzustufen. Zu diesem Zweck geben Sie eine neue GUID-Transaktionspromoter-ID für die neue <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType>-Überladung an. Wenn dieser Vorgang erfolgreich ist, unterliegt die Transaktionsfunktionalität gewissen Einschränkungen. Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, lösen die folgenden Methoden eine <xref:System.Transactions.TransactionPromotionException> aus, da diese Methoden die Höherstufung auf MSDTC erfordern:

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, muss er mit dauerhaften Eintragungen verwendet werden. Dabei werden die von ihm definierten Protokolle verwendet. Die <xref:System.Guid> des Transaktionspromoters kann mithilfe der <xref:System.Transactions.Transaction.PromoterType%2A>-Eigenschaft abgerufen werden. Bei der Höherstufung der Transaktion stellt der Transaktionspromoter ein <xref:System.Byte>-Array bereit, das das höher gestufte Token darstellt. Eine Anwendung kann das höher gestufte Token für eine nicht von MSDTC höher gestufte Transaktion mit der <xref:System.Transactions.Transaction.GetPromotedToken%2A>-Methode abrufen.

Benutzer der neuen <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType>-Überladung müssen eine bestimmte Aufruffolge einhalten, damit die Höherstufung erfolgreich abgeschlossen wird. Diese Regeln werden in der Dokumentation der Methode beschrieben.

<a name="Profile461" />

### <a name="profiling"></a>Profilerstellung

Die nicht verwaltete Profilerstellungs-API wurde wie folgt erweitert:

- Bessere Unterstützung für den Zugriff auf PDBs in der [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md)-Schnittstelle.

  In ASP.NET Core werden Assemblys im Arbeitsspeicher immer häufiger mit Roslyn kompiliert. Für Entwickler von Profilertools bedeutet dies, dass PDB-Dateien, die früher auf Datenträgern serialisiert wurden, u. U. nicht mehr vorkommen. Profilertools verwenden PDB-Dateien häufig, um Codezeilen wieder den Quellzeilen zuzuordnen, beispielsweise für die Codeabdeckung oder zeilenweise Leistungsanalysen. Die [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md)-Schnittstelle enthält jetzt zwei neue Methoden, [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) und [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), um diesen Profilertools Zugriff auf die PDB-Daten im Arbeitsspeicher zu gewähren. Mithilfe der neuen APIs kann ein Profiler Inhalte einer im Arbeitsspeicher enthaltenen PDB-Datei als Bytearray abrufen und dieses anschließend verarbeiten oder auf den Datenträger serialisieren.

- Bessere Instrumentierung mit der ICorProfiler-Schnittstelle.

  Profiler, die die ReJit-Funktionalität der `ICorProfiler`-APIs für die dynamische Instrumentation verwenden, sind jetzt in der Lage, einige Metadaten zu ändern. Früher konnte IL durch diese Tools jederzeit instrumentiert werden, während Metadaten nur zur Ladezeit des Moduls geändert werden konnten. Da IL auf Metadaten verweist, sind die möglichen Instrumentationsarten eingeschränkt. Wir haben einige dieser Beschränkungen durch Hinzufügen der [ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)-Methode aufgehoben. Dadurch werden einige Metadatenbearbeitungen nach dem Laden des Moduls ermöglicht, insbesondere das Hinzufügen neuer `AssemblyRef`-, `TypeRef`-, `TypeSpec`-, `MemberRef`-, `MemberSpec`- und `UserString`-Datensätze. Diese Änderung erweitert die Möglichkeiten der dynamischen Instrumentation.

<a name="NGEN461" />

### <a name="native-image-generator-ngen-pdbs"></a>NGEN (Native Image Generator)-PDBs

Die computerübergreifende Ereignisablaufverfolgung ermöglicht Kunden die Profilerstellung für ein Programm auf Computer A und die Anzeige der Profilerstellungsdaten per Quellzeilenzuordnung auf Computer B. Unter früheren .NET Framework-Versionen musste der Benutzer alle Module und systemeigenen Images vom Profilcomputer auf den Analysecomputer kopieren, der die IL PDB-Datei für die Zuordnung zwischen Quellzeilen und systemeigenen Images enthielt. Während dies bei kleineren Dateien wie Handy-Apps durchaus gut funktionieren kann, können Desktopsystemdateien ziemlich anwachsen und beträchtliche Zeit für das Kopieren erfordern.

Bei NGEN PDB-Dateien kann NGen eine PDB-Datei erstellen, die die Zuordnung zwischen IL und systemeigenen Images enthält, ohne dass eine Abhängigkeit von der IL PDB-Datei besteht. In diesem Szenario für die computerübergreifende Ereignisablaufverfolgung muss lediglich die von Computer A generierte PDB-Datei für systemeigene Images auf Computer B kopiert werden, und die [Debug Interface Access-APIs](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) müssen verwendet werden, um die „Quellzeilen-zu-IL“-Zuordnung der IL PDB-Datei und die „IL-zu-systemeigene Images“-Zuordnung der PDB-Datei für systemeigene Images zu lesen. Durch die Kombination beider Zuordnungen entsteht eine Zuordnung zwischen Quellzeilen und systemeigenem Image. Da die PDB-Datei für systemeigene Images viel kleiner als alle Module und systemeigenen Images ist, wird das Kopieren von Computer A auf Computer B deutlich beschleunigt.

<a name="v46" />

## <a name="whats-new-in-net-2015"></a>Neuigkeiten in .NET 2015

.NET Framework 2015 führt .NET Framework 4.6 und .NET Core ein. Einige neue Features gelten für beide, während andere Funktionen für .NET Framework 4.6 bzw. .NET Core spezifisch sind.

- **ASP.NET Core**

  .NET 2015 enthält ASP.NET Core, eine schlanke .NET-Implementierung zum Erstellen moderner cloudbasierter Apps. ASP.NET Core ist modular aufgebaut, sodass Sie nur die Features aufnehmen können, die Sie in Ihrer Anwendung benötigen. Sie kann auf IIS oder eigenständig in einem benutzerdefinierten Prozess gehostet werden, und Sie können Apps mit verschiedenen Versionen von .NET Framework auf demselben Server ausführen. Sie umfasst ein neues Umgebungskonfigurationssystem, das für die Cloudbereitstellung entwickelt wurde.

  MVC, Web-API und Webseiten sind in einem einzigen Framework namens MVC 6 vereint. Sie erstellen ASP.NET Core-Apps mithilfe von Tools in Visual Studio 2015 oder höher. Ihre vorhandenen Anwendungen funktionieren im neuen .NET Framework. Um jedoch eine App zu erstellen, die MVC 6 oder SignalR 3 verwendet, müssen Sie das Projektsystem in Visual Studio 2015 oder höher verwenden.

  Weitere Informationen finden Sie unter [Einführung in ASP.NET Core](/aspnet/core/).

- **Updates für ASP.NET**

  - **Aufgabenbasierte API für die asynchrone Antwortleerung**

    ASP.NET verfügt nun mit <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType> über eine einfache aufgabenbasierte API für die asynchrone Antwortleerung. Hiermit wird mithilfe der `async/await`-Unterstützung für Ihre Sprache die asynchrone Leerung von Antworten ermöglicht.

  - **Die Modellbindung unterstützt Methoden, die Tasks zurückgeben**

    In .NET Framework 4.5 wurde ASP.NET das Modellbindungsfeature hinzugefügt, das einen erweiterbaren, codeorientierten Ansatz für CRUD-basierte Datenvorgänge in Web Forms-Seiten und Benutzersteuerelementen ermöglicht. Das Modellbindungssystem unterstützt nun wiederkehrende <xref:System.Threading.Tasks.Task>-Modellbindungsmethoden. Dadurch erhalten Web Forms-Entwickler die Vorteile hinsichtlich der Asynchronität und die Einfachheit des Datenbindungssystems beim Verwenden neuerer Versionen von ORMs, einschließlich des Entity Frameworks.

    Die asynchrone Modellbindung wird durch die `aspnet:EnableAsyncModelBinding`-Konfigurationseinstellung gesteuert.

    ```xml
    <appSettings>
        <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
    </appSettings>
    ```

    Bei auf .NET Framework 4.6 ausgerichteten Apps wird der Standardwert auf `true` festgelegt. Bei Apps in .NET Framework 4.6, die auf eine frühere Version von .NET Framework ausgerichtet sind, ist `false` der Standard. Dies kann aktiviert werden, indem die Konfigurationseinstellung auf `true` festgelegt wird.

  - **HTTP/2-Unterstützung (Windows 10)**

    [HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) ist eine neue Version des HTTP-Protokolls, die eine wesentlich bessere Nutzung von Verbindungen ermöglicht (weniger Roundtrips zwischen Client und Server) und so die Latenz beim Laden von Webseiten für Benutzer verringert.  Webseiten profitieren am meisten von HTTP/2 (im Gegensatz zu Services), da das Protokoll Anforderungen mehrerer Artefakte in einem Aufruf zusammenfasst und so optimiert. Die HTTP/2-Unterstützung wurde zu ASP.NET in .NET Framework 4.6 hinzugefügt. Da Netzwerkfunktionen auf mehreren Ebenen vorhanden sind, waren neue Funktionen in Windows, IIS und ASP.NET erforderlich, um HTTP/2 nutzen zu können. Sie müssen Windows 10 ausführen, um HTTP/2 mit ASP.NET nutzen zu können.

    HTTP/2 wird auch unterstützt und ist standardmäßig für Windows 10-UWP-Apps aktiviert, die die <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-API verwenden.

    Zum Bereitstellen einer Möglichkeit für die Verwendung des Features [PUSH_PROMISE](https://http2.github.io/http2-spec/#PUSH_PROMISE) in ASP.NET-Anwendungen wurde der <xref:System.Web.HttpResponse>-Klasse eine neue Methode mit zwei Überladungen (<xref:System.Web.HttpResponse.PushPromise%28System.String%29> und <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>) hinzugefügt.

    > [!NOTE]
    > Während ASP.NET Core Unterstützung für HTTP/2 enthält, wurde noch keine Unterstützung für das PUSH PROMISE-Feature hinzugefügt.

    Browser und Webserver (IIS unter Windows) erledigen die gesamte Arbeit. Sie müssen keine umfangreichen Aufgaben für Ihre Benutzer ausführen.

    Die meisten [gängigen Browser unterstützen HTTP/2](https://www.wikipedia.org/wiki/HTTP/2), sodass Ihre Benutzer wahrscheinlich vom HTTP/2-Protokoll profitieren können, sofern Ihr Server dies unterstützt.

  - **Unterstützung für das Tokenbindungsprotokoll**

    Microsoft und Google haben gemeinsam einen neuen Ansatz für die Authentifizierung erarbeitet, das so genannte [Tokenbindungsprotokoll](https://github.com/TokenBinding/Internet-Drafts). Die Prämisse: Authentifizierungstoken (im Browsercache) können von Internetkriminellen gestohlen und verwendet werden, um auf ansonsten sichere Ressourcen (z. B. Bankkonten) zuzugreifen, ohne Ihr Kennwort oder andere geschützte Informationen zu kennen. Das neue Protokoll zielt darauf ab, dieses Problem zu minimieren.

    Das Tokenbindungsprotokoll wird in Windows 10 als Browserfunktion implementiert. ASP.NET-Anwendungen werden in das Protokoll einbezogen, damit die Legitimität von Authentifizierungstoken überprüft werden kann. Die Client- und Serverimplementierungen stellen den durch das Protokoll angegebenen umfassenden Schutz bereit.

  - **Zufällige Zeichenfolgen-Hashalgorithmen**

    Mit .NET Framework 4.5 wurde ein [zufälliger Zeichenfolgen-Hashalgorithmus](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md) eingeführt. Dieser wurde jedoch durch ASP.NET nicht unterstützt, da einige der ASP.NET von einem stabilen Hash abhängig sind. In .NET Framework 4.6 werden nun zufällige Zeichenfolgen-Hashalgorithmen unterstützt. Verwenden Sie zum Aktivieren dieses Features die `aspnet:UseRandomizedStringHashAlgorithm`-Konfigurationseinstellung.

    ```xml
    <appSettings>
        <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
    </appSettings>
    ```

- **ADO.NET**

  ADO .NET unterstützt jetzt das in SQL Server 2016 Community Technology Preview 2 (CTP2) verfügbare Feature zum grundsätzlichen Verschlüsseln. Mit der grundsätzlichen Verschlüsselung kann SQL Server Operationen zu verschlüsselten Daten durchführen und das Beste ist, der Verschlüsselungsschlüssel ist bei der Anwendung in der vertrauenswürdigen Umgebung des Kunden abgelegt, nicht auf dem Server. Die grundsätzliche Verschlüsselung sichert Kundendaten so, dass DBAs keinen Zugriff auf Textdaten haben. Die Verschlüsselung und Entschlüsselung von Daten erfolgt transparent auf Treiberebene, dadurch werden die an vorhandenen Anwendungen erforderlichen Änderungen auf ein Mindestmaß reduziert. Weitere Informationen finden Sie unter [Always Encrypted (Datenbank-Engine)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) und [Always Encrypted (Cliententwicklung)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **64-Bit-JIT-Compiler für verwalteten Code**

  .NET Framework 4.6 umfasst eine neue Version des 64-Bit-JIT-Compilers (ursprünglicher Codename „RyuJIT“). Der neue 64-Bit-Compiler bietet erhebliche Leistungsverbesserungen im Vergleich zum älteren 64-Bit-JIT-Compiler. Der neue 64-Bit-Compiler wird für 64-Bit-Prozesse aktiviert, die zusätzlich zu .NET Framework 4.6 ausgeführt werden. Ihre App wird in einem 64-Bit-Prozess ausgeführt, wenn sie als 64 Bit oder AnyCPU kompiliert ist und auf einem 64-Bit-Betriebssystem ausgeführt wird. Obwohl der Übergang zum neuen Compiler so transparent wie möglich verlief, sind Änderungen im Verhalten möglich. Wir möchten Sie bitten, uns direkt über Probleme zu informieren, die beim Verwenden des neuen JIT-Compilers auftreten. Kontaktieren Sie uns über [Microsoft Connect](https://connect.microsoft.com/), wenn Sie ein Problem feststellen, das möglicherweise mit dem neuen 64-Bit-JIT-Compiler zusammenhängt.

  Der neue 64-Bit-Compiler umfasst zudem Hardware-SIMD-Beschleunigungsfeatures, wenn er mit SIMD-fähigen Typen im <xref:System.Numerics>-Namespace gekoppelt wird, was zu Leistungsverbesserungen führen kann.

- **Verbesserungen am Assemblyladeprogramm**

  Das Assemblyladeprogramm verwendet nun den Arbeitsspeicher effizienter, indem IL-Assemblys entladen werden, nachdem ein entsprechendes NGEN-Image geladen wurde. Durch diese Änderung wird der virtuelle Arbeitsspeicher verringert. Dies ist besonders bei großen 32-Bit-Apps (wie Visual Studio) hilfreich. Zudem wird dadurch physischer Arbeitsspeicher eingespart.

- **Änderungen an Basisklassenbibliotheken**

  Viele neue APIs wurden im Umfeld von .NET Framework 4.6 hinzugefügt, um wichtige Szenarien zu ermöglichen. Dazu zählen die folgenden Änderungen und Ergänzungen:

  - **IReadOnlyCollection\<T>-Implementierungen**

    Zusätzliche Auflistungen implementieren <xref:System.Collections.Generic.IReadOnlyCollection%601> wie z. B. <xref:System.Collections.Generic.Queue%601> und <xref:System.Collections.Generic.Stack%601>.

  - **CultureInfo.CurrentCulture und CultureInfo.CurrentUICulture**

    Die Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> sind jetzt schreib- und lesbar, statt schreibgeschützt. Wenn Sie diesen Eigenschaften ein neues <xref:System.Globalization.CultureInfo>-Objekt zuweisen, ändern sich ebenfalls die aktuelle Threadkultur, die durch die Eigenschaft `Thread.CurrentThread.CurrentCulture` definiert ist, sowie die aktuelle UI-Threadkultur, die durch die Eigenschaft `Thread.CurrentThread.CurrentUICulture` definiert ist.

  - **Verbesserungen bei der Garbage Collection (GC)**

    Die <xref:System.GC>-Klasse enthält nun die Methoden <xref:System.GC.TryStartNoGCRegion%2A> und <xref:System.GC.EndNoGCRegion%2A>, die es Ihnen ermöglichen, die Garbage Collection während der Ausführung eines kritischen Pfads zu unterbinden.

    Eine neue Überladung der <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType>-Methode erlaubt Ihnen die Kontrolle, ob für den kleinen und großen Objektheap eine Komprimierung und ein Sweep ausgeführt werden, ober ob nur ein Sweep für sie ausgeführt wird.

  - **SIMD-fähige Typen**

    Der <xref:System.Numerics>-Namespace enthält nun eine Reihe von SIMD-fähigen Datentypen wie <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> und <xref:System.Numerics.Vector4>.

    Da der neue 64-Bit-JIT-Compiler zudem Hardware-SIMD-Beschleunigungsfeatures enthält, liegen insbesondere erhebliche Leistungsverbesserungen beim Verwenden von SIMD-fähigen Typen mit dem neuen 64-Bit-JIT-Compiler vor.

  - **Kryptografieupdates**

    Die <xref:System.Security.Cryptography?displayProperty=nameWithType>-API wird aktualisiert, um die [Kryptografie-APIs von Windows CNG](/windows/desktop/SecCNG/cng-reference) zu unterstützen. Frühere Versionen von .NET Framework basierten vollständig auf einer [früheren Version der Kryptografie-APIs](/windows/desktop/SecCrypto/cryptography-portal) von Windows als Grundlage für die <xref:System.Security.Cryptography?displayProperty=nameWithType>-Implementierung. Benutzer forderten die Unterstützung der CNG-API, da diese [moderne Kryptografiealgorithmen](/windows/desktop/SecCNG/cng-features#suite-b-support) unterstützt, die für bestimmte Kategorien von Apps wichtig sind.

    .NET Framework 4.6 umfasst die folgenden neuen Erweiterungen, um die Kryptografie-API von Windows CNG zu unterstützen:

    - Ein Satz von Erweiterungsmethoden für X509-Zertifikate, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` und `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, die nach Möglichkeit anstelle einer CAPI-basierten Implementierung eine CNG-basierte Implementierung zurückgeben. (Für einige Smartcards usw. ist weiterhin CAPI erforderlich, und die APIs verarbeiten den Fallback).

    - Die <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>-Klasse, die eine CNG-Implementierung des RSA-Algorithmus bereitstellt.

    - Erweiterungen an der RSA-API, damit für allgemeine Aktionen keine Umwandlung mehr erforderlich ist. Beispielsweise war für das Verschlüsseln von Daten mithilfe eines <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Objekts Code wie der folgende in vorherigen Versionen von .NET Framework erforderlich.

      [!code-csharp[WhatsNew.Casting#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
      [!code-vb[WhatsNew.Casting#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

      Code, der die neuen Kryptografie-APIs in .NET Framework 4.6 verwendet, kann wie folgt umgeschrieben werden, um die Umwandlung zu vermeiden.

      [!code-csharp[WhatsNew.Casting#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
      [!code-vb[WhatsNew.Casting#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

  - **Unterstützung für das Konvertieren von Datumsangaben und Uhrzeiten zur oder aus der Unix-Zeit**

    Die folgenden neuen Methoden wurden zur <xref:System.DateTimeOffset>-Struktur hinzugefügt, um das Konvertieren von Datums- und Uhrzeitangaben zur oder aus der Unix-Zeit zu unterstützen:

    - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

  - **Kompatibilitätsoptionen**

    Die neue <xref:System.AppContext>-Klasse fügt eine neue Kompatibilitätsfunktion hinzu, die es Bibliotheksautoren ermöglicht, ihren Benutzern einen einheitlichen Abwahlmechanismus für neue Funktionalitäten bereitzustellen. Sie richtet einen lose gekoppelten Vertrag zwischen den Komponenten ein, um eine Anforderung zur Abwahl zu übermitteln. Diese Möglichkeit ist in der Regel wichtig, wenn vorhandene Funktionalitäten verändert werden. Im Gegensatz dazu existiert bereits eine implizite Auswahloption für neue Funktionalitäten.

    Mit <xref:System.AppContext> definieren Bibliotheken Kompatibilitätsoptionen und machen diese verfügbar, während im Code, der von diesen Bibliotheken abhängig ist, diese Optionen festgelegt werden können, um das Verhalten der Bibliothek zu beeinflussen. Standardmäßig stellen Bibliotheken die neue Funktionalität bereit. Nur wenn die Option festgelegt ist, stellen sie die vorherige Funktionalität bereit.

    Eine Anwendung (oder eine Bibliothek) kann den Wert einer Option deklarieren (hierbei handelt es sich immer um einen <xref:System.Boolean>-Wert), die von einer abhängige Bibliothek definiert wird. Die Option ist immer implizit `false`. Durch Festlegen der Option auf `true` wird diese aktiviert. Durch explizites Festlegen der Option auf `false` wird das neue Verhalten aktiviert.

    ```csharp
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
    ```

    ```vb
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", True)
    ```

    Die Bibliothek muss überprüfen, ob ein Consumer den Wert der Option deklariert hat, und dann entsprechend reagieren.

    ```csharp
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
    else
    {
        // new code
    }
    ```

    ```vb
    If Not AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", shouldThrow) Then
        ' This is the case where the switch value was not set by the application.
        ' The library can choose to get the value of shouldThrow by other means.
        ' If no overrides nor default values are specified, the value should be 'false'.
        ' A false value implies the latest behavior.
    End If

    ' The library can use the value of shouldThrow to throw exceptions or not.
    If shouldThrow Then
        ' old code
    Else
        ' new code
    End If
    ```

    Es empfiehlt sich, ein konsistentes Format für Optionen zu verwenden, da es sich hierbei um eine formellen Vertrag handelt, der von einer Bibliothek verfügbar gemacht wird. Das folgende Beispiel zeigt zwei offensichtliche Formate.

    - *Switch*.*namespace*.*switchname*

    - *Switch*.*library*.*switchname*

  - **Änderungen am aufgabenbasierten asynchronen Entwurfsmuster (TAP)**

    Bei Apps für .NET Framework 4.6 erben <xref:System.Threading.Tasks.Task>- und <xref:System.Threading.Tasks.Task%601>-Objekte die Kultur und die Benutzeroberflächenkultur des aufrufenden Threads. Das Verhalten von Apps, die mit früheren Versionen von .NET Framework arbeiten oder auf keine bestimmte Version von .NET Framework ausgelegt sind, ist davon nicht betroffen. Weitere Informationen finden Sie im Abschnitt "Kultur und aufgabenbasierte asynchrone Vorgänge" im Thema zur <xref:System.Globalization.CultureInfo>-Klasse.

    Die <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType>-Klasse ermöglicht Ihnen das Darstellen von Umgebungsdaten, die für eine angegebene asynchrone Ablaufsteuerung wie eine `async`-Methode lokal sind. Sie kann zum threadübergreifenden Beibehalten von Daten verwendet werden. Sie können zudem eine Rückrufmethode definieren, die benachrichtigt wird, sobald sich die Umgebungsdaten ändern, und zwar entweder aufgrund der expliziten Änderung der <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType>-Eigenschaft oder weil der Thread einen Kontextübergang ermittelt hat.

    Dem aufgabenbasierten asynchronem Muster (Task-based Asynchronous Pattern, TAP) wurden die drei Hilfsmethoden <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType> hinzugefügt, um abgeschlossene Aufgaben in einem bestimmten Status zurückzugeben.

    Die <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse unterstützt nun die asynchrone Kommunikation mit der zugehörigen <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A> -Methode.

  - **EventSource unterstützt jetzt das Schreiben in das Ereignisprotokoll**

    Sie können nun die <xref:System.Diagnostics.Tracing.EventSource>-Klasse verwenden, um Verwaltungs- oder betriebliche Nachrichten in das Ereignisprotokoll zu schreiben, und zwar zusätzlich zu vorhandenen auf dem Computer erstellten ETW-Sitzungen. Früher mussten Sie das „Microsoft.Diagnostics.Tracing.EventSource“-NuGet-Paket für diese Funktionalität verwenden. Diese Funktionalität ist nun in .NET Framework 4.6 integriert.

    Sowohl das NuGet-Paket als auch .NET Framework 4.6 wurden mit den folgenden Features aktualisiert:

    - **Dynamische Ereignisse**

      Ermöglichen das „spontane“ Definieren von Ereignissen, und zwar ohne das Erstellen von Ereignismethoden.

    - **Umfangreiche Nutzlasten**

      Ermöglicht, dass speziell attributierte Klassen und Arrays sowie primitive Typen als eine Nutzlast übergeben werden.

    - **Aktivitätsnachverfolgung**

      Löst Start- und Stoppereignisse aus, um Ereignisse zwischen ihnen mit einer ID zu kennzeichnen, die alle aktuell aktiven Aktivitäten darstellt.

    Zum Unterstützen dieses Features wurde der <xref:System.Diagnostics.Tracing.EventSource>-Klasse die überladene <xref:System.Diagnostics.Tracing.EventSource.Write%2A>-Methode hinzugefügt.

- **Windows Presentation Foundation (WPF)**

  - **HDPI-Verbesserungen**

    Die HDPI-Unterstützung in WPF ist in .NET Framework 4.6 nun besser. Es wurden Änderungen an der Layoutglättung vorgenommen, um die Instanzen von Clipping in Steuerelementen mit Begrenzungen zu reduzieren. Standardmäßig wird dieses Feature nur aktiviert, wenn <xref:System.Runtime.Versioning.TargetFrameworkAttribute> auf „.NET 4.6“ festgelegt ist.  Anwendungen, die auf frühere Versionen des Frameworks ausgerichtet sind, aber in .NET Framework 4.6 ausgeführt werden, können das neue Verhalten übernehmen, indem die folgende Zeile zum Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Datei „app.config“ hinzugefügt wird:

    ```xml
    <AppContextSwitchOverrides
    value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
    />
    ```

    Sich auf mehrere Monitore erstreckende WPF-Fenster mit unterschiedlichen DPI-Einstellungen (Multi-DPI-Einrichtung) wurden nun vollständig gerendert, und zwar ohne verdunkelte Bereiche. Sie können dieses Verhalten deaktivieren, indem Sie die folgende Zeile zum `<appSettings>`-Abschnitt der Datei „app.config“ hinzufügen, um dieses neue Verhalten zu deaktivieren:

    ```xml
    <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    ```

    Unterstützung für das automatische Lade des richtigen Cursors, und zwar abhängig davon, ob die DPI-Einstellung zu <xref:System.Windows.Input.Cursor?displayProperty=nameWithType> hinzugefügt wurde.

  - **Toucheingabe ist besser**

    Über [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) meldet der Kunde, dass das unvorhersehbare Verhalten der Toucheingabe in .NET Framework 4.6 behoben wurde. Der Schwellenwert für das Doppeltippen für Windows Store- und WPF-Anwendungen entspricht nun dem in Windows 8.1 und höher.

  - **Unterstützung für das transparente untergeordnete Fenster**

    WPF in .NET Framework 4.6 unterstützte transparente untergeordnete Fenster in Windows 8.1 und höher. Dadurch können Sie untergeordnete Fenster, die weder viereckig noch transparent sind, in Ihren Fenstern auf oberster Ebene erstellen. Sie können diese Funktion aktivieren, indem Sie die <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType>-Eigenschaft auf `true` festlegen.

- **Windows Communication Foundation (WCF)**

  - **SSL-Unterstützung**

    WCF unterstützt nun SSL Version TLS 1.1 und TLS 1.2 neben SSL 3.0 und TLS 1.0 beim Verwenden von NetTcp mit Transportsicherheit und Clientauthentifizierung. Es ist nun möglich, auszuwählen, welches Protokoll verwendet werden soll, oder ältere und zugleich unsicherere Protokolle zu deaktivieren. Dies kann durch das Einstellen der <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A>-Eigenschaft oder durch das Hinzufügen der folgenden Elemente zu einer Konfigurationsdatei erfolgen.

    ```xml
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

  - **Senden von Nachrichten mithilfe von unterschiedlichen HTTP-Verbindungen**

    WCF ermöglicht Benutzern nun, sicherzustellen, dass bestimmte Nachrichten unter Verwendung von zugrunde liegenden HTTP-Verbindungen gesendet wurden. Hierfür gibt es zwei Möglichkeiten:

    - **Verwenden eines Verbindungsgruppen-Namenspräfix**

      Benutzer können eine Zeichenfolge angeben, die WCF als ein Präfix für den Verbindungsgruppennamen verwendet. Unter Verwendung von unterschiedlichen zugrunde liegenden HTTP-Verbindungen werden zwei Nachrichten mit unterschiedlichen Präfixen gesendet. Sie legen das Präfix fest, indem Sie ein Schlüssel-/Wert-Paar zur <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType>-Eigenschaft der Nachricht hinzufügen. Der Schlüssel ist „HttpTransportConnectionGroupNamePrefix“ und der Wert ist das gewünschte Präfix.

    - **Verwenden von unterschiedlichen Kanalfaktoren**

      Benutzer können zudem ein Feature aktivieren, das sicherstellt, dass die mithilfe von anhand unterschiedlicher Kanalfaktoren erstellten Kanälen gesendeten Nachrichten unterschiedliche zugrunde liegende HTTP-Verbindungen verwenden. Zum Aktivieren dieses Features müssen die Benutzer die folgende `appSetting` auf `true` festlegen:

      ```xml
      <appSettings>
          <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
      </appSettings>
      ```

- **Windows Workflow Foundation (WWF)**

  Sie können nun die Anzahl der Sekunden angeben, die ein Workflowdienst an einer gestörten Vorgangsanforderung festhält, wenn ein ausstehendes Nicht-Protokoll-Lesezeichen vorliegt, bevor für die Anforderung ein Timeout ausgelöst wird. Ein "Nicht-Protokoll-Lesezeichen" ist ein Lesezeichen, das nicht mit ausstehenden Receive-Aktivitäten verknüpft ist. Bei einigen Aktivitäten werden Nicht-Protokoll-Lesezeichen in ihrer Implementierung erstellt. Es ist daher ggf. nicht offensichtlich, ob ein Nicht-Protokoll-Lesezeichen vorhanden ist. Dazu zählen der Status und die Auswahl. Wenn Sie über einen Workflowdienst verfügen, der mit einem Statuscomputer implementiert wurde oder eine Auswahlaktivität enthält, verfügen Sie sehr wahrscheinlich über Nicht-Protokoll-Lesezeichen. Sie geben das Intervall an, indem Sie eine Zeile wie die folgende zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen:

  ```xml
  <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
  ```

  Der Standardwert beträgt 60 Sekunden. Wenn `value` auf „0“ festgelegt ist, werden gestörte Anforderungen sofort mit einem Fehlertext abgelehnt, der wie folgt aussieht:

  ```console
  Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.
  ```

  Hierbei handelt es sich um dieselbe Meldung, die Sie empfangen, wenn Sie eine Meldung in Bezug auf einen gestörten Vorgang empfangen und keine Nicht-Protokoll-Lesezeichen vorliegen.

  Wenn der Wert des `FilterResumeTimeoutInSeconds`-Elements nicht null entspricht, liegen keine Nicht-Protokoll-Lesezeichen vor, und das Timeoutintervall läuft ab, wobei beim Vorgang Fehler auftreten und eine Timeoutmeldung angezeigt wird.

- **Transaktionen**

  Sie können die ID für die verteilte Transaktion nun für die Transaktion einbeziehen, die eine Ausnahme verursacht hat, die von der auszulösenden <xref:System.Transactions.TransactionException> abgeleitet wurde. Hierzu müssen Sie den folgenden Schlüssel zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen.

  ```xml
  <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>
  ```

  Der Standardwert ist `false`sein.

- **Netzwerk**

  - **Socket-Wiederverwendung**

    Windows 10 umfasst einen neuen hochskalierbaren Netzwerkalgorithmus, der eine bessere Verwendung von Computerressourcen ermöglicht, indem lokale Ports für ausgehende TCP-Verbindungen verwendet werden. .NET Framework 4.6 unterstützt den neuen Algorithmus, wodurch .NET-Apps von diesem neuen Verhalten profitieren können. In früheren Windows-Versionen gab es einen Grenzwert für gleichzeitige, künstliche Verbindungen (für gewöhnlich 16.384, die Standardgröße des dynamischen Portbereichs), wodurch die Skalierbarkeit eines Diensts begrenzt werden konnte, indem unter Lastbedingungen eine Portauslastung verursacht werden konnte.

    In .NET Framework 4.6 wurden zwei neue APIs hinzugefügt, um die Portwiederverwendung zu aktivieren, wodurch die Begrenzung von 64.000 für gleichzeitige Verbindungen effektiv aufgehoben wurde:

    - Der <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType>-Enumerationswert.

    - Die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>-Eigenschaft

    Standardmäßig lautet die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>-Eigenschaft `false`, sofern der `HWRPortReuseOnSocketBind`-Wert des `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319`-Registrierungsschlüssels nicht auf „0x1“ festgelegt ist. Legen Sie zum Aktivieren der lokalen Portwiederverwendung bei HTTP-Verbindungen die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>-Eigenschaft auf `true` fest. Dadurch verwenden alle ausgehenden TCP-Socketverbindungen von <xref:System.Net.Http.HttpClient> und <xref:System.Net.HttpWebRequest> die neue Windows 10-Socketoption [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options), die die lokale Portwiederverwendung ermöglicht.

    Entwickler, die Nur-Socketanwendungen schreiben, können die <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType>-Option beim Aufrufen einer Methode wie <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> angeben, sodass die ausgehenden Sockets die lokale Ports während der Bindung erneut verwenden.

  - **Unterstützung für internationale Domänennamen und PunyCode**

    Der Klasse <xref:System.Uri> wurde die neue Eigenschaft <xref:System.Uri.IdnHost%2A> hinzugefügt, um internationale Domänennamen und PunyCode besser zu unterstützen.

- **Größenänderungen in Windows Forms-Steuerelementen**

  Dieses Feature wurde in .NET Framework 4.6 so erweitert, dass die Typen <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.ToolStripSplitButton> sowie das durch die <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A>-Eigenschaft festgelegte Rechteck enthalten sind, das beim Zeichnen von <xref:System.Drawing.Design.UITypeEditor> verwendet wird.

  Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Unterstützung für Codepagecodierungen**

  .NET Core unterstützt primär Unicode-Codierungen und bietet standardmäßig eingeschränkte Unterstützung für Codepagecodierungen. Sie können Unterstützung für Codeseitencodierungen, die in .NET Framework verfügbar sind, aber in .NET Core nicht unterstützt werden, verfügbar machen, indem Sie Codeseitencodierungen mit der <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType>-Methode registrieren. Weitere Informationen finden Sie unter <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.

- **.NET Native**

  Windows-Apps für Windows 10, die auf .NET Core ausgerichtet und in C# oder Visual Basic geschrieben sind, können eine neue Technologie nutzen, die Apps in systemeigenen Code kompiliert statt in IL. Sie erzeugen Apps, die sich durch kürzere Start- und Ausführungszeiten auszeichnen. Weitere Informationen finden Sie unter [Kompilieren von Anwendungen mit .NET Native](../net-native/index.md). Eine Übersicht über .NET Native, in der untersucht wird, wie es sich sowohl von der JIT-Kompilierung als auch von NGEN unterscheidet und was dies für Ihren Code bedeutet, finden Sie unter [.NET Native und Kompilierung](../net-native/net-native-and-compilation.md).

  Ihre Apps werden beim Kompilieren mit Visual Studio 2015 oder höher standardmäßig in nativen Code kompiliert. Weitere Informationen finden Sie unter [Erste Schritte mit .NET Native](../net-native/getting-started-with-net-native.md).

  Um das Debuggen von .NET Native-Apps zu unterstützen, wurden der API für nicht verwaltetes Debugging eine Reihe neuer Schnittstellen und Enumerationen hinzugefügt. Weitere Informationen finden Sie im Thema [Debuggen (Referenz zur nicht verwalteten API)](../unmanaged-api/debugging/index.md).

- **Open-Source-Pakete von .NET Framework**

  .NET Core-Pakete wie „immutable collections“, [SIMD-APIs](https://go.microsoft.com/fwlink/?LinkID=518639) und Netzwerk-APIs wie diejenigen aus dem <xref:System.Net.Http>-Namespace stehen jetzt auf [GitHub](https://github.com/) als Open Source-Pakete zur Verfügung. Informationen zum Codezugriff finden Sie unter [CoreFx auf GitHub](https://github.com/dotnet/corefx). Weitere Informationen und wie Sie zu diesen Paketen beitragen können, finden Sie unter [.NET Core und Open-Source](../get-started/net-core-and-open-source.md), [.NET-Homepage auf GitHub](https://github.com/dotnet/home).

<a name="v452" />

## <a name="whats-new-in-net-framework-452"></a>Neuerungen in .NET Framework 4.5.2

- **Neue APIs für ASP.NET-Apps** Mit den neuen <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType>- und <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType>-Methoden können Sie Antwortheader und Statuscodes betrachten und verändern, wenn Sie die Antwort an die Client-App übergeben. Sie sollten diese Methoden anstelle der <xref:System.Web.HttpApplication.PreSendRequestHeaders>- und <xref:System.Web.HttpApplication.PreSendRequestContent>-Ereignisse verwenden, da diese effizienter und zuverlässiger sind.

  Mit der <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType>-Methode können Sie die Ausführung kleiner Hintergrundarbeitselemente planen. ASP.NET überwacht diese Aufgaben und verhindert, dass IIS den Arbeitsprozess abrupt beendet, bevor alle Hintergrundarbeitselemente abgeschlossen wurden. Diese Methode kann nicht außerhalb von verwalteten ASP.NET-App-Domänen aufgerufen werden.

  Die neuen <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType>- und <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType>-Eigenschaften geben boolesche Werte zurück, die angeben, ob die Antwortheader geschrieben wurden. Mit diesen Eigenschaften können Sie sicherstellen, dass API-Aufrufe wie z. B. <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (die Ausnahmen auslösen, wenn die Header geschrieben wurden) erfolgreich ausgeführt werden.

- **Größenänderungen in Windows Forms-Steuerelementen** Dieses Feature wurde erweitert. Sie können nun die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten der folgenden zusätzlichen Steuerelemente anzupassen (z. B. der Dropdownpfeil in Combofeldern):

  - <xref:System.Windows.Forms.ComboBox>
  - <xref:System.Windows.Forms.ToolStripComboBox>
  - <xref:System.Windows.Forms.ToolStripMenuItem>
  - <xref:System.Windows.Forms.Cursor>
  - <xref:System.Windows.Forms.DataGridView>
  - <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

  Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Neues Workflow-Feature** Ein Ressourcen-Manager, der die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Methode verwendet (und somit die <xref:System.Transactions.IPromotableSinglePhaseNotification>-Schnittstelle implementiert), kann die neue <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType>-Methode verwenden, um Folgendes abzufragen:

  - Stufen Sie die Transaktion zu einer Microsoft Distributed Transaction Coordinator (MSDTC)-Transaktion herauf.

  - Ersetzen Sie <xref:System.Transactions.IPromotableSinglePhaseNotification> durch eine <xref:System.Transactions.ISinglePhaseNotification>, eine dauerhafte Eintragung, die einphasige Commits unterstützt.

  Dies kann innerhalb derselben App-Domäne erfolgen, und erfordert keinen zusätzlichen nicht verwalteten Code für die Interaktion mit MSDTC für die Höherstufung. Die neue Methode kann nur aufgerufen werden, wenn ein ausstehender Aufruf von <xref:System.Transactions?displayProperty=nameWithType> an die <xref:System.Transactions.IPromotableSinglePhaseNotification> `Promote`-Methode vorhanden ist, die von der heraufstufbaren Eintragung implementiert wird.

- **Profilerstellungsverbesserungen** Die folgenden neuen, nicht verwalteten Profilerstellungs-APIs bieten eine robustere Profilerstellung:

  - [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](../unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
  - [COR_PRF_HIGH_MONITOR-Enumeration](../unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)
  - [GetAssemblyReferences-Methode](../unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
  - [GetEventMask2-Methode](../unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
  - [SetEventMask2-Methode](../unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
  - [AddAssemblyReference-Methode](../unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

  Frühere `ICorProfiler`-Implementierungen unterstützten Lazy Loading für abhängige Assemblys. Die neue Profilerstellungs-API benötigt abhängige Assemblys, die vom Profiler zum sofortigen Laden eingefügt werden, anstatt nach der vollständigen Initialisierung der App geladen zu werden. Diese Änderung betrifft keine Benutzer der existierenden `ICorProfiler`-APIs.

- **Verbesserungen beim Debugging** Die folgenden neuen, nicht verwalteten Debugging-APIs bieten bessere Profilerintegration. Beim Debuggen von Abbildern haben Sie nun Zugriff auf die vom Profiler eingefügten Metadaten sowie auf lokale Variablen und den von ReJIT-Anfragen des Compilers eingefügten Code.

  - [SetWriteableMetadataUpdateMode-Methode](../unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
  - [EnumerateLocalVariablesEx-Methode](../unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)
  - [GetLocalVariableEx-Methode](../unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)
  - [GetCodeEx-Methode](../unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)
  - [GetActiveReJitRequestILCode-Methode](../unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)
  - [GetInstrumentedILMap-Methode](../unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Änderungen an der Ereignisablaufverfolgung** .NET Framework 4.5.2 unterstützt eine prozessexterne auf der Ereignisablaufverfolgung für Windows (EWT) basierende Aktivitätsverfolgung für eine größere Oberfläche. Auf diese Weise können Advanced Power Management (APM)-Hersteller einfache Tools zur Messung der Kosten einzelner threadübergreifender Anfragen und Aktivitäten anbieten.  Diese Ereignisse werden nur ausgelöst, wenn sie von einem ETW-Controller aktiviert wurden. Die Änderungen betreffen daher keinen zuvor geschriebenen ETW-Code oder Code, der mit deaktivierter ETW ausgeführt wird.

- **Höherstufen einer Transaktion mit entsprechender Konvertierung zu einer dauerhaften Eintragung**

  <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> ist eine neue API, die .NET Framework 4.5.2 und 4.6 hinzugefügt wurde:

  ```csharp
  [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
  public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                            IPromotableSinglePhaseNotification promotableNotification,
                                            ISinglePhaseNotification enlistmentNotification,
                                            EnlistmentOptions enlistmentOptions)
  ```

  ```vb
  <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")>
  public Function PromoteAndEnlistDurable(resourceManagerIdentifier As Guid,
                                          promotableNotification As IPromotableSinglePhaseNotification,
                                          enlistmentNotification As ISinglePhaseNotification,
                                          enlistmentOptions As EnlistmentOptions) As Enlistment
  ```

  Diese Methode wird möglicherweise durch eine Eintragung verwendet, die zuvor durch <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> als Antwort auf die <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>-Methode erstellt wurde. Sie fragt `System.Transactions` ab, um die Transaktion zu einer MSDTC-Transaktion heraufzustufen und um die heraufstufbare Eintragung zu einer dauerhaften Eintragung zu „konvertieren“. Nachdem die Methode erfolgreich abgeschlossen wurde, wird die <xref:System.Transactions.IPromotableSinglePhaseNotification>-Schnittstelle nicht mehr durch `System.Transactions` referenziert, und alle künftigen Benachrichtigungen gelangen zur angegebenen <xref:System.Transactions.ISinglePhaseNotification>-Schnittstelle. Die entsprechende Eintrag muss als eine dauerhafte Eintragung fungieren und die Transaktionsprotokollierung und -wiederherstellung unterstützen. Unter <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> finden Sie entsprechende Einzelheiten. Darüber hinaus muss die Eintragung <xref:System.Transactions.ISinglePhaseNotification> unterstützen.  Diese Methode kann *nur* während der Verarbeitung eines <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>-Aufrufs aufgerufen werden. Wenn dies nicht der Fall ist, wird eine <xref:System.Transactions.TransactionException>-Ausnahme ausgelöst.

<a name="v451" />

## <a name="whats-new-in-net-framework-451"></a>Neuerungen in .NET Framework 4.5.1

**Updates für April 2014**:

- [Visual Studio 2013 Update 2](https://go.microsoft.com/fwlink/p/?LinkId=393658) enthält Updates für die Vorlagen der portablen Klassenbibliothek, um die folgenden Szenarien zu unterstützen:

  - Sie können die Windows-Runtime APIs in portablen Bibliotheken einsetzen, die Windows 8.1, Windows Phone 8.1 und Windows Phone Silverlight 8.1 als Ziel verwenden.

  - Sie können XAML (Windows.UI.XAML-Typen) in portablen Bibliotheken einsetzen, wenn Sie Windows 8.1 oder Windows Phone 8.1 als Ziel verwenden. Die folgenden XAML-Vorlagen werden unterstützt:  Leere Seite, Ressourcenverzeichnis, Steuerelement mit Vorlagen und Benutzersteuerelement.

  - Sie können eine portable Komponente für Windows-Runtime (.winmd-Datei) für den Einsatz in Store-Apps erstellen, die Windows 8.1 und Windows Phone 8.1 als Ziel verwenden.

  - Sie können eine Windows Store- oder Windows Phone Store-Klassenbibliothek wie eine portable Klassenbibliothek neu zuweisen.

  Weitere Informationen zu diesen Änderungen finden Sie unter [Portable Klassenbibliothek](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- Der .NET Framework-Inhaltssatz enthält nun Dokumentation für .NET Native, eine Vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-Apps. .NET Native kompiliert Ihre Apps direkt zu nativem Code anstatt zu einer Intermediate Language (IL) und erzielt dadurch eine bessere Leistung. Details hierzu finden Sie unter [Kompilieren von Anwendungen mit .NET Native](../net-native/index.md).

- Die [.NET Framework-Verweisquelle](https://referencesource.microsoft.com/) bietet ein neues Browsererlebnis und erweiterte Funktionen. Sie können den Quellcode von .NET Framework online durchsuchen, die [Referenz herunterladen](https://referencesource.microsoft.com/download.html), um diese offline anzuzeigen, und den Quellcode (inklusive Patches und Updates) beim Debuggen schrittweise durchlaufen. Weitere Informationen finden Sie im Blogeintrag [A new look for .NET Reference Source](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/).

Die Basisklassen in .NET Framework 4.5.1 weisen die folgenden neuen Features und Verbesserungen auf:

- Automatische Bindungsumleitung für Assemblys. Ab Visual Studio 2013 können beim Kompilieren einer App, die auf .NET Framework 4.5.1 ausgerichtet ist, Bindungsumleitungen zur App-Konfigurationsdatei hinzugefügt werden, wenn die App oder ihre Komponenten sich auf mehrere Versionen derselben Assembly beziehen. Sie können diese Funktion auch für Projekte aktivieren, die frühere Versionen von .NET Framework als Ziel haben. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Fähigkeit, Diagnoseninformationen zu erfassen, um Entwicklern zu helfen, die Leistung von Server- und Cloud-Anwendungen zu verbessern. Weitere Informationen finden Sie unter den <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A>- und <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A>-Methoden in der <xref:System.Diagnostics.Tracing.EventSource>-Klasse.

- Fähigkeit, während einer Garbage Collection den großen Objektheap (Large Object Heap, LOH) explizit zu komprimieren. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>-Eigenschaft.

- Zusätzliche Leistungsverbesserungen wie ASP.NET-App-Unterbrechung, Multikern-JIT-Verbesserungen und schnellere App-Starts nach einem .NET Framework-Update. Ausführliche Informationen finden Sie in der [.NET Framework 4.5.1-Ankündigung](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) und im Blogbeitrag [ASP.NET App Suspend](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/).

Verbesserungen für Windows Forms-Anwendungen:

- Größenänderungen in Windows Forms-Steuerelementen. Sie können die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten von Steuerelementen anzupassen (z. B. die Symbole in einem Eigenschaftenraster), indem Sie diese Funktion über einen Eintrag in der Anwendungskonfigurationsdatei (app.config) für Ihre App aktivieren. Dieses Feature wird zurzeit für die folgenden Windows Forms-Steuerelemente unterstützt:

  - <xref:System.Windows.Forms.PropertyGrid>
  - <xref:System.Windows.Forms.TreeView>
  - Einige Aspekte von <xref:System.Windows.Forms.DataGridView> (weitere unterstützte Steuerelemente finden Sie unter [Neue Features in 4.5.2](#v452))

  Fügen Sie ein neues \<appSettings>-Element zur Konfigurationsdatei (app.config) hinzu und setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element auf `true`, um dieses Feature zu aktivieren:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

Zu Verbesserungen beim Debuggen Ihrer .NET Framework-Apps in Visual Studio 2013 zählen u. a.:

- Rückgabewerte im Visual Studio-Debugger. Wenn Sie eine verwaltete App in Visual Studio 2013 debuggen, werden Rückgabetypen und -werte für Methoden im Fenster „Auto“ angezeigt. Diese Informationen sind für Desktop-, Windows Store- und Windows Phone-Apps verfügbar. Weitere Informationen finden Sie unter [Überprüfen von Rückgabewerten der Methodenaufrufe](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120)).

- "Bearbeiten und Fortfahren" für 64-Bit-Apps. Visual Studio 2013 unterstützt die Funktion „Bearbeiten und fortfahren“ für verwaltete 64-Bit-Apps für Desktops, Windows Store und Windows Phone. Die vorhandenen Einschränkungen bleiben für 32-Bit- und 64-Bit-Apps wirksam (siehe den letzten Abschnitt des Artikels [Unterstützte Codeänderungen (C#)](/visualstudio/debugger/supported-code-changes-csharp)).

- Async-bewusstes Debuggen. Um das Debuggen asynchroner Apps in Visual Studio 2013 zu vereinfachen, wird der Infrastrukturcode, der von Compilern zur Unterstützung asynchronen Programmierens bereitgestellt wird, in der Aufrufliste ausgeblendet. Ebenfalls erfolgt dort eine Verkettung mit logisch übergeordneten Rahmen, sodass der logischen Programmausführung übersichtlicher gefolgt werden kann. Ein Aufgabenfenster ersetzt das Fenster "Parallele Aufgaben" und zeigt Aufgaben an, die sich auf einen bestimmten Haltepunkt beziehen. Außerdem werden alle anderen Aufgaben angezeigt, die momentan aktiv oder in der App geplant sind. Informationen zu diesem Feature finden Sie im Abschnitt „Async-bewusstes Debuggen“ in der [.NET Framework 4.5.1-Ankündigung](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

- Bessere Ausnahmeunterstützung für Windows-Runtime-Komponenten. In [!INCLUDE[win81](../../../includes/win81-md.md)] behalten Ausnahmen, die sich aus Windows Store-Apps ergeben, Informationen zum Fehler, der die Ausnahme ausgelöst hat, sogar über Sprachgrenzen bei. Informationen zu diesem Feature finden Sie im Abschnitt „Windows Store-App-Entwicklung“ in der [.NET Framework 4.5.1-Ankündigung](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

Ab Visual Studio 2013 können Sie zusätzlich das [Managed Profile Guided Optimization Tool (Mpgo.exe)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) verwenden, um sowohl Windows 8.x Store-Apps als auch Desktop-Apps zu optimieren.

Informationen zu neuen Features in ASP.NET 4.5.1 finden Sie unter [ASP.NET and Web Tools for Visual Studio 2013 Release Notes (ASP.NET and Web Tools für Visual Studio 2013: Versionshinweise)](/aspnet/visual-studio/overview/2013/release-notes).

<a name="v45" />

## <a name="whats-new-in-net-framework-45"></a>Neuerungen in .NET Framework 4.5

### <a name="base-classes"></a>Basisklassen

- Weniger Systemneustarts durch Erkennen und Schließen von .NET Framework 4-Anwendungen bei der Bereitstellung. Siehe [Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen](../deployment/reducing-system-restarts.md).

- Unterstützung von mehr als 2 Gigabyte (GB) großen Arrays auf 64-Bit-Plattformen. Sie können die Funktion in der Anwendungskonfiguration aktivieren. Siehe das [\<gcAllowVeryLargeObjects>-Element](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), das auch andere Einschränkungen zur Objekt- und Arraygröße auflistet.

- Bessere Leistung durch Garbage Collection im Hintergrund für Server. Wenn Sie die Garbage Collection auf dem Server in .NET Framework 4.5 verwenden, wird die Garbage Collection im Hintergrund automatisch aktiviert. Siehe im Abschnitt „Garbage Collection auf dem Server im Hintergrund“ des Themas [Grundlagen der Garbage Collection](../../standard/garbage-collection/fundamentals.md).

- Just-In-Time (JIT)-Kompilierung im Hintergrund zur Verbesserung der Anwendungsleistung, die optional auf Mehrkernprozessoren verfügbar ist. Siehe <xref:System.Runtime.ProfileOptimization>.

- Festlegen der Zeit, die die Engine für reguläre Ausdrücke zum Auflösen eines regulären Ausdrucks bis zum Timeout benötigen darf. Siehe <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType>-Eigenschaft.

- Definieren der Standardkultur für eine Anwendungsdomäne. Weitere Informationen finden Sie unter der <xref:System.Globalization.CultureInfo>-Klasse.

- Konsolenunterstützung für Unicode-Codierung (UTF-16). Weitere Informationen finden Sie unter der <xref:System.Console>-Klasse.

- Unterstützung für die Versionierung kulturabhängiger Zeichenfolgenreihenfolgen und -vergleichsdaten. Weitere Informationen finden Sie unter der <xref:System.Globalization.SortVersion>-Klasse.

- Bessere Leistung beim Abrufen von Ressourcen. Siehe [Verpacken und Bereitstellen von Ressourcen](../resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Verbesserte ZIP-Komprimierung zur Reduzierung der Größe einer komprimierten Datei. Siehe <xref:System.IO.Compression?displayProperty=nameWithType>-Namespace.

- Anpassen von Reflektionskontext zum Überschreiben des Standardreflektionsverhaltens mit der <xref:System.Reflection.Context.CustomReflectionContext>-Klasse.

- Unterstützung der Version 2008 des IDNA-Standards (Internationalized Domain Names in Applications) beim Verwenden der <xref:System.Globalization.IdnMapping?displayProperty=nameWithType>-Klasse in [!INCLUDE[win8](../../../includes/win8-md.md)].

- Delegieren des Zeichenfolgenvergleichs an das Betriebssystem, wobei Unicode 6.0 implementiert wird, wenn .NET Framework in [!INCLUDE[win8](../../../includes/win8-md.md)] verwendet wird. Bei Ausführung auf anderen Plattformen verwendet .NET Framework eigene Zeichenfolgenvergleichsdaten, wobei Unicode 5.x. implementiert wird. Siehe <xref:System.String>-Klasse und den Abschnitt "Hinweise" der <xref:System.Globalization.SortVersion>-Klasse.

- Berechnen der Hashcodes für Zeichenfolgen pro Anwendungsdomäne. Siehe [\<UseRandomizedStringHashAlgorithm>-Element](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Typspiegelung unterstützt eine Teilung zwischen <xref:System.Type> und <xref:System.Reflection.TypeInfo>-Klassen. Siehe [Reflektion in .NET Framework für Windows Store-Apps](../reflection-and-codedom/reflection-for-windows-store-apps.md).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

In .NET Framework 4.5 bietet das Managed Extensibility Framework (MEF) folgende neuen Features:

- Unterstützung von generischen Typen.

- Konventionsbasiertes Programmiermodell zum Erstellen von Teilen auf Grundlage von Namenskonventionen anstelle von Attributen.

- Mehrere Bereiche.

- Eine Teilmenge von MEF, die Sie verwenden können, wenn Sie Windows 8.x Store-Apps erstellen. Diese Teilmenge steht als [herunterladbares Paket](https://go.microsoft.com/fwlink/?LinkId=256238) in der NuGet Gallery zur Verfügung. Öffnen Sie zum Installieren des Pakets das Projekt in Visual Studio, wählen Sie im Menü **Projekt** die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Composition`-Paket.

Weitere Informationen finden Sie unter [Übersicht über das Managed Extensibility Framework](../mef/index.md).

### <a name="asynchronous-file-operations"></a>Asynchrone Dateivorgänge

In .NET Framework 4.5 wurden neue asynchrone Features den Programmiersprachen C# und Visual Basic hinzugefügt. Diese Funktionen ergänzen ein aufgabenbasiertes Modell zum Ausführen von asynchronen Vorgängen. Verwenden Sie dieses neue Modell mithilfe der asynchronen Methoden in den E/A-Klassen. Siehe [Asynchrone Datei-E/A](../../standard/io/asynchronous-file-i-o.md).

<a name="tools" />

### <a name="tools"></a>Tools

In .NET Framework 4.5 können Sie mit dem Resource File Generator-Tool (Resgen.exe) aus einer RESOURCES-Datei, die in einer .NET Framework-Assembly eingebettet ist, eine RESW-Datei für Windows 8.x Store-Apps erstellen. Weitere Informationen finden Sie unter [Resgen.exe (Resource File Generator)](../tools/resgen-exe-resource-file-generator.md).

Mit Managed Profile Guided Optimization (Mpgo.exe) können Sie die Anwendungsstartzeit, die Arbeitsspeicherauslastung (Workingsetgröße) und den Durchsatz verbessern, indem Sie die Assemblys systemeigener Abbilder optimieren. Das Befehlszeilentool generiert Profildaten für Anwendungsassemblys systemeigener Abbilder. Siehe [Mpgo.exe (verwaltetes, profilgesteuertes Optimierungstool)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md). Ab Visual Studio 2013 können Sie zusätzlich „Mpgo.exe“ verwenden, um sowohl Windows 8.x Store-Apps als auch Desktop-Apps zu optimieren.

<a name="parallel" />

### <a name="parallel-computing"></a>Parallele Computervorgänge

.NET Framework 4.5 stellt mehrere neue Features und Verbesserungen für parallele Berechnung bereit. Dazu gehören leistungsfähigere, erweiterte Steuerungsmöglichkeiten, verbesserte Unterstützung für asynchrone Programmierung, eine neue Datenflussbibliothek und verbesserte Unterstützung für paralleles Debuggen und Leistungsanalyse. Siehe den Eintrag zu den [Neuerungen hinsichtlich der Parallelität in .NET 4.5](https://go.microsoft.com/fwlink/?LinkId=235061) im Blog zur parallelen Programmierung mit .NET.

<a name="web" />

### <a name="web"></a>Web

In ASP.NET 4.5 und 4.5.1 wurden die Modellbindung für Webformulare, WebSocket-Unterstützung, asynchrone Handler, Leistungserweiterungen und viele weitere Funktionen hinzugefügt. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [ASP.NET 4.5 and Visual Studio 2012 (ASP.NET 4.5 und Visual Studio 2012)](https://docs.microsoft.com/previous-versions/aspnet/hh420390(v=vs.110))

- [ASP.NET and Web Tools für Visual Studio 2013 – Anmerkungen zu dieser Version](/aspnet/visual-studio/overview/2013/release-notes)

### <a name="networking-a-namenetworking-"></a>Netzwerk <a name="networking" />

.NET Framework 4.5 stellt eine neue Programmierschnittstelle für HTTP-Anwendungen bereit. Weitere Informationen finden Sie in den neuen Namespaces <xref:System.Net.Http?displayProperty=nameWithType> und <xref:System.Net.Http.Headers?displayProperty=nameWithType>.

Unterstützt wird jetzt auch eine neue Programmierschnittstelle, um eine WebSocket-Verbindung mithilfe der vorhandenen <xref:System.Net.HttpListener>-Klasse und verknüpften Klassen anzunehmen und mit dieser zu interagieren. Weitere Informationen finden Sie im neuen <xref:System.Net.WebSockets>-Namespace und in der <xref:System.Net.HttpListener>-Klasse.

Darüber hinaus bietet .NET Framework 4.5 folgende Netzwerkverbesserungen:

- RFC-kompatible URI-Unterstützung. Weitere Informationen finden Sie in der <xref:System.Uri>-Klasse und verknüpften Klassen.

- Unterstützung für IDN (Internationalized Domain Name)-Analysen. Weitere Informationen finden Sie in der <xref:System.Uri>-Klasse und verknüpften Klassen.

- Unterstützung für E-Mail-Adressen-Internationalisierung (EAI). Weitere Informationen finden Sie unter den Ausführungen zum <xref:System.Net.Mail>-Namespace.

- Verbesserte IPv6-Unterstützung. Weitere Informationen finden Sie unter den Ausführungen zum <xref:System.Net.NetworkInformation>-Namespace.

- Dual-Modus-Socket-Unterstützung. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Net.Sockets.Socket>-Klasse und zur <xref:System.Net.Sockets.TcpListener>-Klasse.

<a name="client" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.5 wurde Windows Presentation Foundation (WPF) in vielen Bereichen überarbeitet und verbessert. Dazu gehören:

- Das neue <xref:System.Windows.Controls.Ribbon.Ribbon>-Steuerelement, mit dem Sie eine Menüband-Benutzeroberfläche implementieren können, die eine Symbolleiste für den Schnellzugriff, ein Anwendungsmenü und Registerkarten hostet.

- Die neue <xref:System.ComponentModel.INotifyDataErrorInfo>-Schnittstelle, die synchrone und asynchrone Datenvalidierung unterstützt.

- Neue Funktionen für die <xref:System.Windows.Controls.VirtualizingPanel>- und <xref:System.Windows.Threading.Dispatcher>-Klassen.

- Verbesserte Leistung beim Anzeigen großer Datengruppierungen sowie durch den Zugriff auf Auflistungen in Nicht-UI-Threads.

- Datenbindung an statische Eigenschaften, Datenbindung an benutzerdefinierte Typen, die die <xref:System.Reflection.ICustomTypeProvider>-Schnittstelle implementieren, und Abrufen von Datenbindungsinformationen von einem Bindungsausdruck.

- Neupositionierung von Daten bei Wertänderung (Live-Strukturierung).

- Überprüfen einer möglicherweise getrennten Verbindung des Datenkontexts für einen Elementcontainer.

- Festlegen der Zeit, die zwischen Eigenschaftenänderungen und Datenquellenupdates verstreichen soll.

- Verbesserte Unterstützung für das Implementieren schwacher Ereignismuster. Zudem können Ereignisse jetzt Markuperweiterungen akzeptieren.

<a name="windows_communication_foundation" />

### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

Um das Schreiben und Verwalten von WCF-Anwendungen (Windows Communication Foundation) zu erleichtern, wurden in .NET Framework 4.5 folgende Features hinzugefügt:

- Vereinfachung von generierten Konfigurationsdateien.

- Unterstützung für Contract-First-Entwicklung.

- Leichteres Konfigurieren des ASP.NET-Kompatibilitätsmodus.

- Änderungen in den standardmäßigen Transporteigenschaftswerten, um die Wahrscheinlichkeit zu reduzieren, dass Sie sie festlegen müssen.

- Updates der <xref:System.Xml.XmlDictionaryReaderQuotas>-Klasse, um die Wahrscheinlichkeit zu reduzieren, dass Sie Kontingente für XML-Wörterbuch-Reader manuell konfigurieren müssen.

- Validierung von WCF-Konfigurationsdateien von Visual Studio als Teil des Buildprozesses, sodass Sie Konfigurationsfehler erkennen können, bevor Sie die Anwendung ausführen.

- Neue Unterstützung für asynchrones Streaming.

- Neue HTTPS-Protokollzuordnung zur leichteren Bereitstellung eines Endpunkts über HTTPS mit IIS (Internetinformationsdienste).

- Generieren von Metadaten in einem einzelnen WSDL-Dokument durch Anfügen von `?singleWSDL` an die Dienst-URL.

- Websockets-Unterstützung für echte bidirektionale Kommunikation über die Ports 80 und 443 mit TCP-transportähnlichen Leistungsmerkmalen.

- Unterstützung für das Konfigurieren von Diensten im Code.

- XML-Editor-QuickInfos.

- Unterstützung von <xref:System.ServiceModel.ChannelFactory>-Cachediensten.

- Unterstützung für die Komprimierung binärer Encoder.

- Unterstützung für einen UDP-Transport, mit dem Entwickler "Fire and Forget" (Auslösen und Vergessen)-Messaging-Dienste schreiben können. Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.

- Unterstützung mehrerer Authentifizierungsmodi auf einem einzelnen WCF-Endpunkt beim Verwenden von HTTP-Transport und -Transportsicherheit.

- Unterstützung für WCF-Dienste, die internationale Domänennamen (IDNs) verwenden.

Weitere Informationen finden Sie unter [Neues in Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=228173).

<a name="windows_workflow_foundation" />

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

.NET Framework 4.5 bietet viele neue Features für Windows Workflow Foundation (WF), so z. B.:

- Zustandsautomatworkflows, die zunächst als Teil von .NET Framework 4.0.1 ([.NET Framework 4 Platform-Update 1](https://go.microsoft.com/fwlink/?LinkID=215092)) eingeführt wurden. Dieses Update umfasste mehrere neue Klassen und Aktivitäten, sodass Entwickler Zustandsautomatworkflows erstellen konnten. Diese Klassen und Aktivitäten wurden für .NET Framework 4.5 aktualisiert und umfassen nun Folgendes:

  - Festlegen von Haltepunkten für Zustände.

  - Kopieren und Einfügen von Übergängen im Workflow Designer.

  - Designerunterstützung für das Erstellen von freigegebenen Triggerübergängen.

  - Aktivitäten zum Erstellen von Zustandsautomatworkflows, einschließlich <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> und <xref:System.Activities.Statements.Transition>.

- Verbesserte Workflow Designer-Funktionen, z. B.:

  - Verbesserte Workflowsuchfunktionen in Visual Studio, einschließlich **Schnellsuche** und **In Dateien suchen**.

  - Automatisches Erstellen einer Sequenzaktivität, wenn eine zweite untergeordnete Aktivität zu einer Containeraktivität hinzugefügt wird, und Einschließen beider Aktivitäten in die Sequenzaktivität.

  - Schwenk-Unterstützung zur Änderung des sichtbaren Teils eines Workflows ohne die Verwendung von Bildlaufleisten.

  - Die neue Ansicht **Dokumentgliederung**, die die Gliederungsansicht der Workflowkomponenten in einer Baumstruktur anzeigt und die Auswahl einer Komponente in der Ansicht **Dokumentgliederung** ermöglicht.

  - Hinzufügen von Anmerkungen zu Aktivitäten.

  - Definieren und Verarbeiten von Aktivitätsdelegaten mit dem Workflow Designer.

  - Automatisches Verbinden und Einfügen für Aktivitäten und Übergänge in Zustandsautomaten- und Flussdiagrammworkflows.

- Speichern der Ansichtszustandsinformationen für einen Workflow in einem einzelnen Element in der XAML-Datei, sodass Sie die Ansichtszustandsinformationen leicht finden und bearbeiten können.

- Eine NoPersistScope-Containeraktivität, damit untergeordnete Aktivitäten nicht beibehalten werden.

- Unterstützung von C#-Ausdrücken:

  - Visual Basic-Workflowprojekte verwenden Visual Basic-Ausdrücke, und C#-Workflowprojekte verwenden C#-Ausdrücke.

  - C#-Workflowprojekte, die in Visual Studio 2010 erstellt wurden und Visual Basic-Ausdrücke verwenden, sind mit C#-Workflowprojekten, die C#-Ausdrücke verwenden, kompatibel.

- Versionsverwaltungserweiterungen:

  - Die neue <xref:System.Activities.WorkflowIdentity>-Klasse, die eine Zuordnung zwischen einer beibehaltenen Workflowinstanz und ihrer Workflowdefinition bietet.

  - Parallele Ausführung mehrerer Workflowversionen im selben Host, einschließlich <xref:System.ServiceModel.Activities.WorkflowServiceHost>.

  - Die Änderbarkeit der Definition einer beibehaltenen Workflowinstanz im Rahmen eines dynamischen Updates.

- Contract-First-Workflowdienstentwicklung, die das automatische Generieren von Aktivitäten zur Übereinstimmung mit einem vorhandenen Dienstvertrag unterstützt.

Weitere Informationen finden Sie unter [Neues in Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkId=228176).

<a name="tailored" />

### <a name="net-for-windows-8x-store-apps"></a>.NET für Windows 8.x Store-Apps

Windows 8.x Store-Apps werden für bestimmte Formfaktoren entworfen und nutzen die Leistungsfähigkeit des Windows-Betriebssystems. Eine Teilmenge von .NET Framework 4.5 oder 4.5.1 kann mithilfe von C# oder Visual Basic zum Erstellen von Windows 8.x Store-Apps für Windows verwendet werden. Diese Teilmenge wird .NET for Windows 8.x Store genannt und in einer [Übersicht](https://go.microsoft.com/fwlink/?LinkId=228491) im Windows Developer Center erläutert.

### <a name="portable-class-libraries-a-nameportable-"></a>Portable Klassenbibliotheken <a name="portable" />

Mit dem Projekt „Portable Klassenbibliothek“ in Visual Studio 2012 (und Folgeversionen) können Sie verwaltete Assemblys, die auf mehreren .NET Framework-Plattformen ausgeführt werden können, schreiben und erstellen. Bei Verwenden eines Projekts des Typs „Portable Klassenbibliothek“ wählen Sie die Zielplattformen (wie Windows Phone- und .NET für Windows 8.x Store-Apps) aus. Die verfügbaren Typen und Member im Projekt werden automatisch auf die allgemeinen Typen und Member dieser Plattformen beschränkt. Weitere Informationen finden Sie in der Dokumentation zur [Portablen Klassenbibliothek](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>Siehe auch

- [.NET Framework und Out-of-Band-Releases](../get-started/the-net-framework-and-out-of-band-releases.md)
- [Neuerungen der Barrierefreiheit in .NET Framework](whats-new-in-accessibility.md)
- [Neues in Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [ASP.NET](/aspnet)
- [Neuerungen bei C++ in Visual Studio](/cpp/what-s-new-for-visual-cpp-in-visual-studio)
