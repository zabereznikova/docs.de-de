---
title: 'Gewusst wie: Speichern von asymmetrischen Schlüsseln in einem Schlüsselcontainer'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: 6b703156b38f52513c86f7b2507ac6c185a9dd50
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155944"
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="9a114-102">Gewusst wie: Speichern von asymmetrischen Schlüsseln in einem Schlüsselcontainer</span><span class="sxs-lookup"><span data-stu-id="9a114-102">How to: Store Asymmetric Keys in a Key Container</span></span>
<span data-ttu-id="9a114-103">Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9a114-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="9a114-104">Wenn ein privater Schlüssel gespeichert werden muss, sollten Sie einen Schlüsselcontainer verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a114-104">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="9a114-105">Weitere Informationen zu Schlüsselcontainern finden Sie unter [RSA-Schlüsselcontainer auf Computerebene und Benutzerebene](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9a114-105">For more information on key containers, see [Understanding Machine-Level and User-Level RSA Key Containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="9a114-106">So erstellen Sie einen asymmetrischen Schlüssel und speichern ihn in einem Schlüsselcontainer</span><span class="sxs-lookup"><span data-stu-id="9a114-106">To create an asymmetric key and save it in a key container</span></span>  
  
1. <span data-ttu-id="9a114-107">Erstellen Sie eine neue Instanz einer <xref:System.Security.Cryptography.CspParameters>-Klasse, und übergeben Sie den Namen, den Sie als Schlüssel Container abrufen möchten, an das <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> Feld.</span><span class="sxs-lookup"><span data-stu-id="9a114-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>  
  
2. <span data-ttu-id="9a114-108">Erstellen Sie eine neue Instanz einer Klasse, die von der <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Klasse abgeleitet ist (normalerweise **RSACryptoServiceProvider** oder **DSACryptoServiceProvider**), und übergeben Sie das zuvor erstellte **CspParameters** -Objekt an seinen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9a114-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
### <a name="to-delete-the-key-from-a-key-container"></a><span data-ttu-id="9a114-109">So löschen Sie den Schlüssel aus einem Schlüsselcontainer</span><span class="sxs-lookup"><span data-stu-id="9a114-109">To delete the key from a key container</span></span>  
  
1. <span data-ttu-id="9a114-110">Erstellen Sie eine neue Instanz der **CspParameters**-Klasse, und übergeben Sie den gewünschten Namen für den Schlüsselcontainer an das Feld **CspParameters.KeyContainerName**.</span><span class="sxs-lookup"><span data-stu-id="9a114-110">Create a new instance of a **CspParameters** class and pass the name that you want to call the key container to the **CspParameters.KeyContainerName** field.</span></span>  
  
2. <span data-ttu-id="9a114-111">Erstellen Sie eine neue Instanz einer Klasse, die aus der **AsymmetricAlgorithm**-Klasse abgeleitet ist (normalerweise **RSACryptoServiceProvider** oder **DSACryptoServiceProvider**), und übergeben Sie das zuvor erstellte **CspParameters**-Objekt an deren Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9a114-111">Create a new instance of a class that derives from the **AsymmetricAlgorithm** class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
3. <span data-ttu-id="9a114-112">Legen Sie die **PersistKeyInCSP**-Eigenschaft der Klasse, die aus **AsymmetricAlgorithm** abgeleitet ist, auf **false** fest (**False** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9a114-112">Set the **PersistKeyInCSP** property of the class that derives from **AsymmetricAlgorithm** to **false** (**False** in Visual Basic).</span></span>  
  
4. <span data-ttu-id="9a114-113">Rufen Sie die **Clear**-Methode der Klasse auf, die aus **AsymmetricAlgorithm** abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="9a114-113">Call the **Clear** method of the class that derives from **AsymmetricAlgorithm**.</span></span> <span data-ttu-id="9a114-114">Diese Methode gibt alle Ressourcen der Klasse frei und löscht den Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="9a114-114">This method releases all resources of the class and clears the key container.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a114-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a114-115">Example</span></span>  
 <span data-ttu-id="9a114-116">Das folgende Beispiel zeigt, wie Sie einen asymmetrischen Schlüssel erstellen, ihn in einem Schlüsselcontainer speichern, den Schlüssel zu einem späteren Zeitpunkt abrufen und den Schlüssel aus dem Container löschen.</span><span class="sxs-lookup"><span data-stu-id="9a114-116">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>  
  
 <span data-ttu-id="9a114-117">Beachten Sie, dass der Code in der `GenKey_SaveInContainer`-Methode und der `GetKeyFromContainer`-Methode ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="9a114-117">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span>  <span data-ttu-id="9a114-118">Wenn Sie einen Schlüsselcontainernamen für ein <xref:System.Security.Cryptography.CspParameters>-Objekt angeben und ihn an ein <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Objekt mit auf "true" festgelegten Eigenschaft <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> oder <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> übergeben, geschieht Folgendes.</span><span class="sxs-lookup"><span data-stu-id="9a114-118">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to true, the following occurs.</span></span>  <span data-ttu-id="9a114-119">Wenn kein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird einer erstellt und der Schlüssel wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9a114-119">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>  <span data-ttu-id="9a114-120">Wenn ein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird der der Schlüssel im Container automatisch in der aktuelle <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Objekt geladen.</span><span class="sxs-lookup"><span data-stu-id="9a114-120">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>  <span data-ttu-id="9a114-121">Daher behält der Code in der `GenKey_SaveInContainer`-Methode den Schlüssel bei, weil er zuerst ausgeführt wird, während der Code in der `GetKeyFromContainer`-Methode den Schlüssel lädt, weil er als zweites ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a114-121">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it is run second.</span></span>  
  
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
  
```console  
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a114-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a114-122">See also</span></span>

- [<span data-ttu-id="9a114-123">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="9a114-123">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="9a114-124">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="9a114-124">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)
- [<span data-ttu-id="9a114-125">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="9a114-125">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)
- [<span data-ttu-id="9a114-126">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="9a114-126">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
