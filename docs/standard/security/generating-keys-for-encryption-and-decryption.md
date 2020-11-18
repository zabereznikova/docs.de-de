---
title: Erzeugen von Schlüsseln für die Ver- und Entschlüsselung
description: Erfahren Sie, wie symmetrische und asymmetrische Schlüssel für die Verschlüsselung und Entschlüsselung in .NET erstellt und verwaltet werden.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: aa95204a90f2aee684cdd20095d1816e890a0306
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831077"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Erzeugen von Schlüsseln für die Ver- und Entschlüsselung
Das Erstellen und Verwalten von Schlüsseln ist ein wichtiger Bestandteil des kryptografischen Prozesses. Bei symmetrischen Algorithmen müssen ein Schlüssel und ein Initialisierungsvektor (IV) erstellt werden. Der Schlüssel muss vor Unbefugten, die Ihre Daten nicht entschlüsseln können sollen, geheim gehalten werden. Der IV muss nicht geheim sein, sollte aber für jede Sitzung geändert werden. Bei asymmetrischen Algorithmen müssen ein öffentlicher und ein privater Schlüssel erstellt werden. Der öffentliche Schlüssel kann allgemein zugänglich sein, während der private Schlüssel nur dem Teilnehmer bekannt sein darf, der die mit dem öffentlichen Schlüssel verschlüsselten Daten entschlüsselt. In diesem Abschnitt wird beschrieben, wie Schlüssel für symmetrische und asymmetrische Algorithmen erzeugt und verwaltet werden.  
  
## <a name="symmetric-keys"></a>Symmetrische Schlüssel  
 Für die von .NET bereitgestellten symmetrischen Verschlüsselungs Klassen sind ein Schlüssel und ein neuer Initialisierungs Vektor (IV) erforderlich, um Daten zu verschlüsseln und zu entschlüsseln. Wenn Sie eine neue Instanz einer der verwalteten symmetrischen Kryptografieklassen mithilfe der Parameter losen `Create()` -Methode erstellen, werden automatisch ein neuer Schlüssel und IV erstellt. Alle Benutzer, die zum Entschlüsseln der Daten berechtigt sind, müssen über den gleichen Schlüssel und IV verfügen und den gleichen Algorithmus verwenden. Generell sollten für jede Sitzung ein neuer Schlüssel und IV erstellt und weder Schlüssel noch IV für eine spätere Sitzung gespeichert werden.  
  
 Um den symmetrischen Schlüssel und IV der Gegenseite mitzuteilen, wird der symmetrische Schlüssel in der Regel asymmetrisch verschlüsselt. Das Senden des unverschlüsselten Schlüssels über ein nicht sicheres Netzwerk birgt ein großes Sicherheitsrisiko, da jeder, der den Schlüssel und den IV abfängt, die Daten entschlüsseln kann.  
  
 Das folgende Beispiel zeigt die Erstellung einer neuen Instanz der standardmäßigen Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus.  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 Beim Ausführen des obigen Codes werden ein neuer Schlüssel und IV erzeugt und in die **Key** -Eigenschaft bzw. die **IV** -Eigenschaft aufgenommen.  
  
 Manchmal müssen u. U. mehrere Schlüssel erzeugt werden. In diesem Fall können Sie zuerst eine neue Instanz einer Klasse, durch die ein symmetrischer Algorithmus implementiert wird, erstellen und erzeugen dann durch den Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode einen neuen Schlüssel und IV. Im folgenden Codebeispiel wird veranschaulicht, wie neue Schlüssel und IVS erstellt werden, nachdem eine neue Instanz der symmetrischen Kryptografieklasse erstellt wurde.  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 Wenn der vorangehende Code ausgeführt wird, werden ein Schlüssel und ein IV generiert, wenn die neue Instanz von **AES** erstellt wird. Ein weiterer Schlüssel und ein weiterer IV werden beim Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode erstellt.
  
## <a name="asymmetric-keys"></a>Asymmetrische Schlüssel

 .NET stellt die- <xref:System.Security.Cryptography.RSA> Klasse für die asymmetrische Verschlüsselung bereit. Diese Klasse erstellt ein öffentliches/privates Schlüsselpaar, wenn Sie die Parameter lose- `Create()` Methode verwenden, um eine neue-Instanz zu erstellen. Asymmetrische Schlüssel können entweder nur für eine Sitzung erzeugt oder gespeichert und für mehrere Sitzungen verwendet werden. Während der öffentliche Schlüssel öffentlich verfügbar sein kann, sollte der private Schlüssel streng geheim gehalten werden.  
  
 Bei jedem Erstellen einer neuen Instanz einer asymmetrischen Algorithmusklasse wird ein öffentliches/privates Schlüsselpaar erzeugt. Nachdem eine neue Instanz der-Klasse erstellt wurde, können die Schlüsselinformationen mit der-Methode extrahiert werden <xref:System.Security.Cryptography.RSA.ExportParameters%2A> , die eine-Struktur zurückgibt, die <xref:System.Security.Cryptography.RSAParameters> die Schlüsselinformationen enthält. Die-Methode akzeptiert einen booleschen Wert, der angibt, ob nur die Informationen des öffentlichen Schlüssels oder die Informationen des öffentlichen Schlüssels und des privaten Schlüssels zurückgegeben werden sollen.

Es gibt auch andere Methoden, mit denen Sie wichtige Informationen extrahieren können, wie z. b.:

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

Eine **RSA** -Instanz kann mit dem Wert einer **RSAParameters** -Struktur initialisiert werden, indem die-Methode verwendet wird <xref:System.Security.Cryptography.RSA.ImportParameters%2A> . Oder erstellen Sie eine neue-Instanz, indem Sie die- <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> Methode verwenden.  
  
 Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden. Wenn ein privater Schlüssel gespeichert werden muss, sollten Sie einen Schlüsselcontainer verwenden. Weitere Informationen zum Speichern eines privaten Schlüssels in einem Schlüssel Container finden Sie unter Gewusst [wie: Speichern von asymmetrischen Schlüsseln in einem Schlüssel Container](how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 Im folgenden Codebeispiel wird eine neue Instanz der **RSA** -Klasse erstellt, wodurch ein öffentliches/privates Schlüsselpaar erstellt und die Informationen des öffentlichen Schlüssels in einer **RSAParameters** -Struktur gespeichert werden.  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verschlüsseln von Daten](encrypting-data.md)
- [Entschlüsseln von Daten](decrypting-data.md)
- [Kryptografische Dienste](cryptographic-services.md)
- [Vorgehensweise: Speichern asymmetrischer Schlüssel in einem Schlüsselcontainer](how-to-store-asymmetric-keys-in-a-key-container.md)
- [Plattformübergreifende Kryptografie](cross-platform-cryptography.md)
- [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
