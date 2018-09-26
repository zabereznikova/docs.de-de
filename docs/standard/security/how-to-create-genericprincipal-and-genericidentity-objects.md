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
ms.openlocfilehash: 79b5e05fe9133eb2282eedefa001e64ece5e0f57
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111073"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a>Gewusst wie: Erstellen von GenericPrincipal-Objekten und GenericIdentity-Objekten
Können Sie die <xref:System.Security.Principal.GenericIdentity> Klasse in Verbindung mit der <xref:System.Security.Principal.GenericPrincipal> Klasse, um ein Autorisierungsschema, die vorhanden ist unabhängig von einer Windows-Domäne zu erstellen.  
  
### <a name="to-create-a-genericprincipal-object"></a>So erstellen Sie ein GenericPrincipal-Objekt  
  
1.  Erstellen Sie eine neue Instanz der Identitätsklasse, und initialisieren Sie diese mit dem Namen, der in der Instanz enthalten sein soll. Im folgenden Code wird ein neues **GenericIdentity**-Objekt erstellt und mit dem Namen `MyUser` initialisiert.  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  Erstellen Sie eine neue Instanz der **GenericPrincipal**-Klasse, und initialisieren Sie diese mit dem zuvor erstellten **GenericIdentity**-Objekt und einem Zeichenfolgenarray, das den Rollen entspricht, die Sie diesem Prinzipal zuordnen möchten. Im folgenden Codebeispiel wird ein Array mit Zeichenfolgen definiert, die eine Administrator- und eine Benutzerrolle angeben. Die **GenericPrincipal**-Instanz wird dann mit der vorherigen **GenericIdentity**-Instanz und dem Zeichenfolgenarray initialisiert.  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  Verwenden Sie den folgenden Code, um den Prinzipal an den aktuellen Thread anzufügen. Das ist hilfreich in Situationen, in dem der Prinzipal muss mehrmals überprüft werden, von anderem Code in der Anwendung ausgeführten geprüft werden muss oder es muss geprüft werden, indem, eine <xref:System.Security.Permissions.PrincipalPermission> Objekt. Sie können weiterhin rollenbasierte Überprüfung für das Prinzipalobjekt ausführen, ohne es an den Thread anzufügen. Weitere Informationen finden Sie unter [Ersetzen eines Principalobjekts](../../../docs/standard/security/replacing-a-principal-object.md).  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Instanz von **GenericPrincipal** und **GenericIdentity** erstellt wird. Mit diesem Code werden die Werte dieser Objekte in der Konsole angezeigt.  
  
```vb  
Imports System  
Imports System.Security.Principal  
Imports System.Threading  
  
Public Class Class1  
  
    Public Shared Sub Main()  
        ' Create generic identity.  
        Dim MyIdentity As New GenericIdentity("MyIdentity")  
  
        ' Create generic principal.  
        Dim MyStringArray As String() =  {"Manager", "Teller"}  
        Dim MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
  
        ' Attach the principal to the current thread.  
        ' This is not required unless repeated validation must occur,  
        ' other code in your application must validate, or the   
        ' PrincipalPermisson object is used.   
        Thread.CurrentPrincipal = MyPrincipal  
  
        ' Print values to the console.  
        Dim Name As String = MyPrincipal.Identity.Name  
        Dim Auth As Boolean = MyPrincipal.Identity.IsAuthenticated  
        Dim IsInRole As Boolean = MyPrincipal.IsInRole("Manager")  
  
        Console.WriteLine("The Name is: {0}", Name)  
        Console.WriteLine("The IsAuthenticated is: {0}", Auth)  
        Console.WriteLine("Is this a Manager? {0}", IsInRole)  
  
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
    GenericIdentity MyIdentity = new GenericIdentity("MyIdentity");  
  
    // Create generic principal.  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal =   
        new GenericPrincipal(MyIdentity, MyStringArray);  
  
    // Attach the principal to the current thread.  
    // This is not required unless repeated validation must occur,  
    // other code in your application must validate, or the   
    // PrincipalPermisson object is used.   
    Thread.CurrentPrincipal = MyPrincipal;  
  
    // Print values to the console.  
    String Name =  MyPrincipal.Identity.Name;  
    bool Auth =  MyPrincipal.Identity.IsAuthenticated;   
    bool IsInRole =  MyPrincipal.IsInRole("Manager");  
  
    Console.WriteLine("The Name is: {0}", Name);  
    Console.WriteLine("The IsAuthenticated is: {0}", Auth);  
    Console.WriteLine("Is this a Manager? {0}", IsInRole);  
  
    return 0;  
    }  
}  
```  
  
 Wird die Anwendung ausgeführt, zeit sie in etwa die folgende Ausgabe an.  
  
```  
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
