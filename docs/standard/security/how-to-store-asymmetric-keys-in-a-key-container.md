---
title: "How to: Store Asymmetric Keys in a Key Container | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "cryptography [.NET Framework], asymmetric keys"
  - "storing asymmetric keys"
  - "keys, asymmetric"
  - "encryption keys"
  - "keys, storing in key containers"
  - "asymmetric keys [.NET Framework]"
  - "encryption [.NET Framework], asymmetric keys"
  - "decryption keys"
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Store Asymmetric Keys in a Key Container
Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden.  Wenn ein privater Schlüssel gespeichert werden muss, sollten Sie einen Schlüsselcontainer verwenden.  Weitere Informationen zu Schlüsselcontainern finden Sie unter [Understanding Machine\-Level and User\-Level RSA Key Containers](../Topic/Understanding%20Machine-Level%20and%20User-Level%20RSA%20Key%20Containers.md).  
  
### So erstellen Sie einen asymmetrischen Schlüssel und speichern ihn in einem Schlüsselcontainer  
  
1.  Erstellen Sie eine neue Instanz einer <xref:System.Security.Cryptography.CspParameters>\-Klasse und übergeben Sie den gewünschten Namen des Schlüsselcontainers an das Feld <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=fullName>.  
  
2.  Erstellen Sie eine neue Instanz einer Klasse, die von der <xref:System.Security.Cryptography.AsymmetricAlgorithm>\-Klasse abgeleitet ist \(normalerweise **RSACryptoServiceProvider** oder **DSACryptoServiceProvider**\), und übergeben Sie das zuvor erstellte **CspParameters**\-Objekt an ihren Konstruktor.  
  
### So löschen Sie den Schlüssel aus einem Schlüsselcontainer  
  
1.  Erstellen Sie eine neue Instanz einer **CspParameters**\-Klasse, und übergeben Sie den gewünschten Namen für den Schlüsselcontainer an das Feld **CspParameters.KeyContainerName**.  
  
2.  Erstellen Sie eine neue Instanz einer Klasse, die von der **AsymmetricAlgorithm**\-Klasse abgeleitet ist \(normalerweise **RSACryptoServiceProvider** oder **DSACryptoServiceProvider**\), und übergeben Sie das zuvor erstellte **CspParameters**\-Objekt an ihren Konstruktor.  
  
3.  Legen Sie die Eigenschaft **PersistKeyInCSP** der Klasse, die von **AsymmetricAlgorithm** abgeleitet ist, auf **false** fest \(**False** in Visual Basic\).  
  
4.  Rufen Sie die **Clear**\-Methode der Klasse auf, die von **AsymmetricAlgorithm** abgeleitet ist.  Diese Methode gibt alle Ressourcen der Klasse frei und löscht den Schlüsselcontainer.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen asymmetrischen Schlüssel erstellen, ihn in einem Schlüsselcontainer speichern, den Schlüssel zu einem späteren Zeitpunkt abrufen und den Schlüssel aus dem Container löschen.  
  
 Beachten, dass dieser Code in `GenKey_SaveInContainer`\-Methode und der `GetKeyFromContainer`\-Methode ähnlich ist.  Wenn Sie einen Schlüsselcontainernamen für ein <xref:System.Security.Cryptography.CspParameters>\-Objekt angeben und ihn an ein <xref:System.Security.Cryptography.AsymmetricAlgorithm>\-Objekt mit auf "true" festgelegten Eigenschaft <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> oder <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> übergeben, geschieht Folgendes.  Wenn kein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird einer erstellt und der Schlüssel wird beibehalten.  Wenn ein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird der der Schlüssel im Container automatisch in der aktuelle <xref:System.Security.Cryptography.AsymmetricAlgorithm>\-Objekt geladen.  Daher behält der Code in der `GenKey_SaveInContainer`\-Methode den Schlüssel bei, weil er zuerst ausgeführt wird, während der Code in der `GetKeyFromContainer`\-Methode den Schlüssel lädt, weil er als zweites ausgeführt wird.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```Output  
  
            Zum Container hinzugefügter Schlüssel:  
<RSAKeyValue> Schlüsselinformation A</RSAKeyValue>  
Aus dem Container abgerufener Schlüssel:  
<RSAKeyValue> Schlüsselinformation A</RSAKeyValue>  
Schlüssel gelöscht.  Zum Container hinzugefügter Schlüssel:  
<RSAKeyValue> Schlüsselinformation B</RSAKeyValue>  
Schlüssel gelöscht.    
```  
  
## Siehe auch  
 [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)   
 [Encrypting Data](../../../docs/standard/security/encrypting-data.md)   
 [Decrypting Data](../../../docs/standard/security/decrypting-data.md)   
 [Kryptografische Dienste](../../../docs/standard/security/cryptographic-services.md)