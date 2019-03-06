---
title: 'Vorgehensweise: Erstellen von GenericPrincipal-Objekten und GenericIdentity-Objekten'
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
ms.openlocfilehash: b47f4c093acb094188cbd5a8a0a0026c67eb3f2c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360055"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="1096f-102">Vorgehensweise: Erstellen von GenericPrincipal-Objekten und GenericIdentity-Objekten</span><span class="sxs-lookup"><span data-stu-id="1096f-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

<span data-ttu-id="1096f-103">Können Sie die <xref:System.Security.Principal.GenericIdentity> Klasse in Verbindung mit der <xref:System.Security.Principal.GenericPrincipal> Klasse, um ein Autorisierungsschema, die vorhanden ist unabhängig von einer Windows-Domäne zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1096f-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="1096f-104">So erstellen Sie ein GenericPrincipal-Objekt</span><span class="sxs-lookup"><span data-stu-id="1096f-104">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="1096f-105">Erstellen Sie eine neue Instanz der Identitätsklasse, und initialisieren Sie diese mit dem Namen, der in der Instanz enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="1096f-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="1096f-106">Im folgenden Code wird ein neues **GenericIdentity**-Objekt erstellt und mit dem Namen `MyUser` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="1096f-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="1096f-107">Erstellen Sie eine neue Instanz der **GenericPrincipal**-Klasse, und initialisieren Sie diese mit dem zuvor erstellten **GenericIdentity**-Objekt und einem Zeichenfolgenarray, das den Rollen entspricht, die Sie diesem Prinzipal zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="1096f-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="1096f-108">Im folgenden Codebeispiel wird ein Array mit Zeichenfolgen definiert, die eine Administrator- und eine Benutzerrolle angeben.</span><span class="sxs-lookup"><span data-stu-id="1096f-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="1096f-109">Die **GenericPrincipal**-Instanz wird dann mit der vorherigen **GenericIdentity**-Instanz und dem Zeichenfolgenarray initialisiert.</span><span class="sxs-lookup"><span data-stu-id="1096f-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="1096f-110">Verwenden Sie den folgenden Code, um den Prinzipal an den aktuellen Thread anzufügen.</span><span class="sxs-lookup"><span data-stu-id="1096f-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="1096f-111">Das ist hilfreich in Situationen, in dem der Prinzipal muss mehrmals überprüft werden, von anderem Code in der Anwendung ausgeführten geprüft werden muss oder es muss geprüft werden, indem, eine <xref:System.Security.Permissions.PrincipalPermission> Objekt.</span><span class="sxs-lookup"><span data-stu-id="1096f-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="1096f-112">Sie können weiterhin rollenbasierte Überprüfung für das Prinzipalobjekt ausführen, ohne es an den Thread anzufügen.</span><span class="sxs-lookup"><span data-stu-id="1096f-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="1096f-113">Weitere Informationen finden Sie unter [Ersetzen eines Principalobjekts](../../../docs/standard/security/replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="1096f-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="1096f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1096f-114">Example</span></span>

<span data-ttu-id="1096f-115">Im folgenden Codebeispiel wird veranschaulicht, wie eine Instanz von **GenericPrincipal** und **GenericIdentity** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1096f-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="1096f-116">Mit diesem Code werden die Werte dieser Objekte in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1096f-116">This code displays the values of these objects to the console.</span></span>

```vb
Imports System
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

<span data-ttu-id="1096f-117">Wird die Anwendung ausgeführt, zeit sie in etwa die folgende Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="1096f-117">When executed, the application displays output similar to the following.</span></span>

```
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="1096f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1096f-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="1096f-119">Ersetzen eines Principalobjekts</span><span class="sxs-lookup"><span data-stu-id="1096f-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="1096f-120">Principal- und Identitätsobjekte</span><span class="sxs-lookup"><span data-stu-id="1096f-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
