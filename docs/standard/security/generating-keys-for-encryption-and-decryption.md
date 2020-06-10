---
title: Erzeugen von Schlüsseln für die Ver- und Entschlüsselung
description: Erfahren Sie, wie symmetrische und asymmetrische Schlüssel für die Verschlüsselung und Entschlüsselung in .NET erstellt und verwaltet werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: f8c3633d18e200037235502487d0d91d42083241
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661808"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Erzeugen von Schlüsseln für die Ver- und Entschlüsselung
Das Erstellen und Verwalten von Schlüsseln ist ein wichtiger Bestandteil des kryptografischen Prozesses. Bei symmetrischen Algorithmen müssen ein Schlüssel und ein Initialisierungsvektor (IV) erstellt werden. Der Schlüssel muss vor Unbefugten, die Ihre Daten nicht entschlüsseln können sollen, geheim gehalten werden. Der IV muss nicht geheim sein, sollte aber für jede Sitzung geändert werden. Bei asymmetrischen Algorithmen müssen ein öffentlicher und ein privater Schlüssel erstellt werden. Der öffentliche Schlüssel kann allgemein zugänglich sein, während der private Schlüssel nur dem Teilnehmer bekannt sein darf, der die mit dem öffentlichen Schlüssel verschlüsselten Daten entschlüsselt. In diesem Abschnitt wird beschrieben, wie Schlüssel für symmetrische und asymmetrische Algorithmen erzeugt und verwaltet werden.  
  
## <a name="symmetric-keys"></a>Symmetrische Schlüssel  
 Für die von .NET Framework bereitgestellten symmetrischen Verschlüsselungsklassen sind ein Schlüssel und ein neuer Initialisierungsvektor (IV) erforderlich, damit Daten verschlüsselt und entschlüsselt werden können. Jedes Mal, wenn Sie eine neue Instanz einer der verwalteten symmetrischen Kryptografieklassen mit dem Parameter losen Konstruktor erstellen, werden automatisch ein neuer Schlüssel und IV erstellt. Alle Benutzer, die zum Entschlüsseln der Daten berechtigt sind, müssen über den gleichen Schlüssel und IV verfügen und den gleichen Algorithmus verwenden. Generell sollten für jede Sitzung ein neuer Schlüssel und IV erstellt und weder Schlüssel noch IV für eine spätere Sitzung gespeichert werden.  
  
 Um den symmetrischen Schlüssel und IV der Gegenseite mitzuteilen, wird der symmetrische Schlüssel in der Regel asymmetrisch verschlüsselt. Das Senden des unverschlüsselten Schlüssels über ein nicht sicheres Netzwerk birgt ein großes Sicherheitsrisiko, da jeder, der den Schlüssel und den IV abfängt, die Daten entschlüsseln kann. Weitere Informationen zum verschlüsselten Datenaustausch finden Sie unter [Erstellen eines kryptografischen Schemas](creating-a-cryptographic-scheme.md).  
  
 Im folgenden Beispiel wird eine neue Instanz der <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> -Klasse erstellt, durch die der TripleDES-Algorithmus implementiert wird.  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
```  
  
 Beim Ausführen des obigen Codes werden ein neuer Schlüssel und IV erzeugt und in die **Key** -Eigenschaft bzw. die **IV** -Eigenschaft aufgenommen.  
  
 Manchmal müssen u. U. mehrere Schlüssel erzeugt werden. In diesem Fall können Sie zuerst eine neue Instanz einer Klasse, durch die ein symmetrischer Algorithmus implementiert wird, erstellen und erzeugen dann durch den Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode einen neuen Schlüssel und IV. Im folgenden Codebeispiel wird veranschaulicht, wie neue Schlüssel und IVS erstellt werden, nachdem eine neue Instanz der symmetrischen Kryptografieklasse erstellt wurde.  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
tdes.GenerateIV()  
tdes.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
tdes.GenerateIV();  
tdes.GenerateKey();  
```  
  
 Beim Ausführen des obigen Codes werden beim Erstellen der neuen **TripleDESCryptoServiceProvider** -Instanz ein Schlüssel und IV erzeugt. Ein weiterer Schlüssel und ein weiterer IV werden beim Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode erstellt.  
  
## <a name="asymmetric-keys"></a>Asymmetrische Schlüssel  
 .NET Framework stellt die Klassen <xref:System.Security.Cryptography.RSACryptoServiceProvider> und <xref:System.Security.Cryptography.DSACryptoServiceProvider> für asymmetrische Verschlüsselung bereit. Diese Klassen erstellen ein öffentliches/privates Schlüsselpaar, wenn Sie den Parameter losen Konstruktor verwenden, um eine neue Instanz zu erstellen. Asymmetrische Schlüssel können entweder nur für eine Sitzung erzeugt oder gespeichert und für mehrere Sitzungen verwendet werden. Während der öffentliche Schlüssel öffentlich verfügbar sein kann, sollte der private Schlüssel streng geheim gehalten werden.  
  
 Bei jedem Erstellen einer neuen Instanz einer asymmetrischen Algorithmusklasse wird ein öffentliches/privates Schlüsselpaar erzeugt. Nachdem eine neue Instanz der Klasse erstellt worden ist, können die Schlüsselinformationen mit einer der folgenden beiden Methoden extrahiert werden:  
  
- mit der <xref:System.Security.Cryptography.RSA.ToXmlString%2A> -Methode, die eine XML-Darstellung der Schlüsselinformationen zurückgibt;  
  
- mit der <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> -Methode, die eine <xref:System.Security.Cryptography.RSAParameters> -Struktur mit den Schlüsselinformationen zurückgibt.  
  
 Bei beiden Methoden wird ein boolescher Wert akzeptiert, der angibt, ob nur die Informationen des öffentlichen Schlüssels oder die Informationen beider Schlüssel (öffentlich und privat) zurückgegeben werden sollen. Eine **RSACryptoServiceProvider** -Klasse kann mit dem Wert einer **RSAParameters** -Struktur initialisiert werden, indem die <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> -Methode verwendet wird.  
  
 Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden. Wenn ein privater Schlüssel gespeichert werden muss, sollten Sie einen Schlüsselcontainer verwenden. Weitere Informationen zum Speichern eines privaten Schlüssels in einem Schlüsselcontainer finden Sie unter [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 Im folgenden Codebeispiel wird eine neue Instanz der **RSACryptoServiceProvider** -Klasse erstellt, wodurch ein öffentliches/privates Schlüsselpaar erzeugt wird. Dann werden die Informationen des öffentlichen Schlüssels in einer **RSAParameters-** Struktur gespeichert.  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Verschlüsseln von Daten](encrypting-data.md)
- [Entschlüsseln von Daten](decrypting-data.md)
- [Kryptografiedienste](cryptographic-services.md)
- [Vorgehensweise: Speichern asymmetrischer Schlüssel in einem Schlüsselcontainer](how-to-store-asymmetric-keys-in-a-key-container.md)
