---
title: 'Gewusst wie: Speichern von asymmetrischen Schlüsseln in einem Schlüssel Container'
description: Erfahren Sie, wie Sie asymmetrische Schlüssel in einem Schlüssel Container in .net speichern. Erfahren Sie, wie Sie einen asymmetrischen Schlüssel erstellen, ihn in einem Schlüssel Container speichern und den Schlüssel abrufen und löschen.
ms.date: 05/26/2020
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
ms.openlocfilehash: a0fbde37491043cc1aab71e9733087bf410b997d
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769028"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a>Speichern von asymmetrischen Schlüsseln in einem Schlüssel Container

Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden. Wenn Sie einen privaten Schlüssel speichern müssen, verwenden Sie einen Schlüssel Container. Weitere Informationen zu Schlüssel Containern finden Sie Untergrund Legendes zu [RSA-Schlüssel Containern auf Computer Ebene und Benutzerebene](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a>Erstellen Sie einen asymmetrischen Schlüssel, und speichern Sie ihn in einem Schlüssel Container.

1. Erstellen Sie eine neue Instanz einer <xref:System.Security.Cryptography.CspParameters> -Klasse, und übergeben Sie den Namen, den Sie als Schlüssel Container abrufen möchten, an das- <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> Feld.

1. Erstellen Sie eine neue Instanz einer Klasse, die von der-Klasse abgeleitet wird <xref:System.Security.Cryptography.AsymmetricAlgorithm> (in der Regel <xref:System.Security.Cryptography.RSACryptoServiceProvider> oder <xref:System.Security.Cryptography.DSACryptoServiceProvider> ), und übergeben Sie das zuvor erstellte- `CspParameters` Objekt an den Konstruktor.

> [!NOTE]
> Das Erstellen und Abrufen eines asymmetrischen Schlüssels ist ein Vorgang. Wenn ein Schlüssel nicht bereits im Container vorhanden ist, wird er erstellt, bevor er zurückgegeben wird.
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a>Löschen Sie den Schlüssel aus dem Schlüssel Container.

1. Erstellen Sie eine neue Instanz einer `CspParameters` -Klasse, und übergeben Sie den Namen, den Sie als Schlüssel Container abrufen möchten, an das- <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> Feld.

1. Erstellen Sie eine neue Instanz einer Klasse, die von der-Klasse abgeleitet wird <xref:System.Security.Cryptography.AsymmetricAlgorithm> (in der Regel `RSACryptoServiceProvider` oder `DSACryptoServiceProvider` ), und übergeben Sie das zuvor erstellte- `CspParameters` Objekt an den Konstruktor.

1. Legen Sie die- <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> Eigenschaft oder die- <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> Eigenschaft der Klasse, die von abgeleitet wird, `AsymmetricAlgorithm` auf `false` ( `False` in Visual Basic) fest.

1. Ruft die- `Clear` Methode der-Klasse auf, die von abgeleitet wird `AsymmetricAlgorithm` . Diese Methode gibt alle Ressourcen der Klasse frei und löscht den Schlüsselcontainer.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie einen asymmetrischen Schlüssel erstellen, ihn in einem Schlüsselcontainer speichern, den Schlüssel zu einem späteren Zeitpunkt abrufen und den Schlüssel aus dem Container löschen.

Beachten Sie, dass der Code in der `GenKey_SaveInContainer`-Methode und der `GetKeyFromContainer`-Methode ähnlich ist. Wenn Sie einen Schlüssel Container Namen für ein <xref:System.Security.Cryptography.CspParameters> -Objekt angeben und ihn an ein- <xref:System.Security.Cryptography.AsymmetricAlgorithm> Objekt übergeben, bei dem die-Eigenschaft oder die- <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> Eigenschaft auf festgelegt ist `true` , sieht das Verhalten wie folgt aus:

- Wenn kein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird einer erstellt und der Schlüssel wird beibehalten.
- Wenn ein Schlüsselcontainer mit dem angegebenen Namen vorhanden ist, wird der der Schlüssel im Container automatisch in der aktuelle <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Objekt geladen.

Daher behält der Code in der- `GenKey_SaveInContainer` Methode den Schlüssel bei, weil er zuerst ausgeführt wird, während der Code in der `GetKeyFromContainer` -Methode den Schlüssel lädt, weil er als zweites ausgeführt wird.

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

Die Ausgabe lautet wie folgt:

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

## <a name="see-also"></a>Weitere Informationen

- [Erzeugen von Schlüsseln für die Verschlüsselung und Entschlüsselung](generating-keys-for-encryption-and-decryption.md)
- [Verschlüsseln von Daten](encrypting-data.md)
- [Entschlüsseln von Daten](decrypting-data.md)
- [Kryptografiedienste](cryptographic-services.md)
