---
title: 'Gewusst wie: Speichern von asymmetrischen Schlüsseln in einem Schlüssel Container'
description: Erfahren Sie, wie Sie asymmetrische Schlüssel in einem Schlüssel Container in .net speichern. Erfahren Sie, wie Sie einen asymmetrischen Schlüssel erstellen, ihn in einem Schlüssel Container speichern und den Schlüssel abrufen und löschen.
ms.date: 05/26/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET]
- encryption [.NET], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: aa6fad815338cbd6316deca7be0a23286630fa56
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556292"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="1a3f4-104">Speichern von asymmetrischen Schlüsseln in einem Schlüssel Container</span><span class="sxs-lookup"><span data-stu-id="1a3f4-104">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="1a3f4-105">Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-105">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="1a3f4-106">Wenn Sie einen privaten Schlüssel speichern müssen, verwenden Sie einen Schlüssel Container.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-106">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="1a3f4-107">Weitere Informationen zu Schlüssel Containern finden Sie Untergrund Legendes zu [RSA-Schlüssel Containern auf Computer Ebene und Benutzerebene](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1a3f4-107">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="1a3f4-108">Der Code in diesem Artikel gilt für Windows.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-108">The code in this article applies to Windows.</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="1a3f4-109">Erstellen Sie einen asymmetrischen Schlüssel, und speichern Sie ihn in einem Schlüssel Container.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-109">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="1a3f4-110">Erstellen Sie eine neue Instanz einer <xref:System.Security.Cryptography.CspParameters> -Klasse, und übergeben Sie den Namen, den Sie als Schlüssel Container abrufen möchten, an das- <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> Feld.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-110">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="1a3f4-111">Erstellen Sie eine neue Instanz einer Klasse, die von der-Klasse abgeleitet wird <xref:System.Security.Cryptography.AsymmetricAlgorithm> (in der Regel <xref:System.Security.Cryptography.RSACryptoServiceProvider> oder <xref:System.Security.Cryptography.DSACryptoServiceProvider> ), und übergeben Sie das zuvor erstellte- `CspParameters` Objekt an den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-111">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="1a3f4-112">Das Erstellen und Abrufen eines asymmetrischen Schlüssels ist ein Vorgang.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-112">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="1a3f4-113">Wenn ein Schlüssel nicht bereits im Container vorhanden ist, wird er erstellt, bevor er zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-113">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="1a3f4-114">Löschen Sie den Schlüssel aus dem Schlüssel Container.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-114">Delete the key from the key container</span></span>

1. <span data-ttu-id="1a3f4-115">Erstellen Sie eine neue Instanz einer `CspParameters` -Klasse, und übergeben Sie den Namen, den Sie als Schlüssel Container abrufen möchten, an das- <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> Feld.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-115">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="1a3f4-116">Erstellen Sie eine neue Instanz einer Klasse, die von der-Klasse abgeleitet wird <xref:System.Security.Cryptography.AsymmetricAlgorithm> (in der Regel `RSACryptoServiceProvider` oder `DSACryptoServiceProvider` ), und übergeben Sie das zuvor erstellte- `CspParameters` Objekt an den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-116">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="1a3f4-117">Legen Sie die- <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> Eigenschaft oder die- <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> Eigenschaft der Klasse, die von abgeleitet wird, `AsymmetricAlgorithm` auf `false` ( `False` in Visual Basic) fest.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-117">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="1a3f4-118">Ruft die- `Clear` Methode der-Klasse auf, die von abgeleitet wird `AsymmetricAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="1a3f4-118">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="1a3f4-119">Diese Methode gibt alle Ressourcen der Klasse frei und löscht den Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-119">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="1a3f4-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a3f4-120">Example</span></span>

<span data-ttu-id="1a3f4-121">Das folgende Beispiel zeigt, wie Sie einen asymmetrischen Schlüssel erstellen, ihn in einem Schlüsselcontainer speichern, den Schlüssel zu einem späteren Zeitpunkt abrufen und den Schlüssel aus dem Container löschen.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-121">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="1a3f4-122">Beachten Sie, dass der Code in der `GenKey_SaveInContainer`-Methode und der `GetKeyFromContainer`-Methode ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-122">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="1a3f4-123">Wenn Sie einen Schlüssel Container Namen für ein <xref:System.Security.Cryptography.CspParameters> -Objekt angeben und ihn an ein- <xref:System.Security.Cryptography.AsymmetricAlgorithm> Objekt übergeben, bei dem die-Eigenschaft oder die- <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> Eigenschaft auf festgelegt ist `true` , sieht das Verhalten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1a3f4-123">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="1a3f4-124">Wenn kein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird einer erstellt und der Schlüssel wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-124">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="1a3f4-125">Wenn ein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird der der Schlüssel im Container automatisch in der aktuelle <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Objekt geladen.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-125">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="1a3f4-126">Daher behält der Code in der- `GenKey_SaveInContainer` Methode den Schlüssel bei, weil er zuerst ausgeführt wird, während der Code in der `GetKeyFromContainer` -Methode den Schlüssel lädt, weil er als zweites ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a3f4-126">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

```vb
Imports System
Imports System.Security.Cryptography

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

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
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
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

<span data-ttu-id="1a3f4-127">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1a3f4-127">The output is as follows:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1a3f4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a3f4-128">See also</span></span>

- [<span data-ttu-id="1a3f4-129">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="1a3f4-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="1a3f4-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="1a3f4-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="1a3f4-131">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="1a3f4-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="1a3f4-132">Erzeugen von Schlüsseln für die Verschlüsselung und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="1a3f4-132">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="1a3f4-133">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="1a3f4-133">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="1a3f4-134">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="1a3f4-134">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="1a3f4-135">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="1a3f4-135">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
