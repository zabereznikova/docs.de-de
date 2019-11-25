---
title: 'Gewusst wie: Erstellen von GenericPrincipal-Objekten und GenericIdentity-Objekten'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37f5543ceaca83a024132c5d010b6d969876454f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353827"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a>Gewusst wie: Erstellen von GenericPrincipal-Objekten und GenericIdentity-Objekten

You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.

### <a name="to-create-a-genericprincipal-object"></a>So erstellen Sie ein GenericPrincipal-Objekt

1. Erstellen Sie eine neue Instanz der Identitätsklasse, und initialisieren Sie diese mit dem Namen, der in der Instanz enthalten sein soll. Im folgenden Code wird ein neues **GenericIdentity**-Objekt erstellt und mit dem Namen `MyUser` initialisiert.

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. Erstellen Sie eine neue Instanz der **GenericPrincipal**-Klasse, und initialisieren Sie diese mit dem zuvor erstellten **GenericIdentity**-Objekt und einem Zeichenfolgenarray, das den Rollen entspricht, die Sie diesem Prinzipal zuordnen möchten. Im folgenden Codebeispiel wird ein Array mit Zeichenfolgen definiert, die eine Administrator- und eine Benutzerrolle angeben. Die **GenericPrincipal**-Instanz wird dann mit der vorherigen **GenericIdentity**-Instanz und dem Zeichenfolgenarray initialisiert.

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. Verwenden Sie den folgenden Code, um den Prinzipal an den aktuellen Thread anzufügen. This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object. Sie können weiterhin rollenbasierte Überprüfung für das Prinzipalobjekt ausführen, ohne es an den Thread anzufügen. Weitere Informationen finden Sie unter [Ersetzen eines Principalobjekts](../../../docs/standard/security/replacing-a-principal-object.md).

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, wie eine Instanz von **GenericPrincipal** und **GenericIdentity** erstellt wird. Mit diesem Code werden die Werte dieser Objekte in der Konsole angezeigt.

```vb
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

    End Sub

End Class
```

```csharp
using System;
using System.Security.Principal;
using System.Threading;

public class Class1
{
    public static int Main(string[] args)
    {
    // Create generic identity.
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

Wird die Anwendung ausgeführt, zeit sie in etwa die folgende Ausgabe an.

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [Ersetzen eines Principalobjekts](../../../docs/standard/security/replacing-a-principal-object.md)
- [Principal- und Identitätsobjekte](../../../docs/standard/security/principal-and-identity-objects.md)
