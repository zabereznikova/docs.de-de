---
title: "How to: Create GenericPrincipal and GenericIdentity Objects | Microsoft Docs"
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
  - "Creating Generic Identity Objects"
  - "GenericPrincipal Objects"
  - "Creating GenericPrincipal Objects"
  - "GenericIdentity Objects"
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Create GenericPrincipal and GenericIdentity Objects
Sie können die <xref:System.Security.Principal.GenericIdentity>\-Klasse zusammen mit der <xref:System.Security.Principal.GenericPrincipal>\-Klasse verwenden, um ein von einer Windows NT\- oder Windows 2000\-Dom äne unabhängiges Autorisierungsschema zu erstellen.  
  
### So erstellen Sie ein GenericPrincipal\-Objekt  
  
1.  Erstellen Sie eine neue Instanz der Identitätsklasse, und initialisieren Sie diese mit dem Namen, der in der Instanz abgelegt werden soll.  Im folgenden Code wird ein neues **GenericIdentity**\-Objekt erstellt und mit dem Namen `MyUser` initialisiert.  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  Erstellen Sie eine neue Instanz der **GenericPrincipal**\-Klasse. Initialisieren Sie sie mit dem zuvor erstellten **GenericIdentity**\-Objekt und einem Zeichenfolgenarray, das die diesem Prinzipal zuzuordnenden Rollen darstellt.  Im folgenden Codebeispiel wird ein Zeichenfolgenarray definiert, dessen Zeichenfolgen eine Administrator\- und eine Benutzerrolle darstellen.  Das **GenericPrincipal** wird anschließend mit der vorherigen **GenericIdentity** sowie dem Zeichenfolgenarray initialisiert.  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  Verwenden Sie folgenden Code, um den Prinzipal an den aktuellen Thread anzufügen.  Dies ist dann hilfreich, wenn der Principal mehrmals bzw. durch anderen in der Anwendung ausgeführten Code oder durch ein <xref:System.Security.Permissions.PrincipalPermission>\-Objekt geprüft werden muss.  Sie können auch eine rollenbasierte Validierung für das Principalobjekt durchführen, ohne es an den Thread anzufügen.  Weitere Informationen finden Sie unter [Ersetzen eines Principalobjekts](../../../docs/standard/security/replacing-a-principal-object.md).  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Erstellen einer Instanz von **GenericPrincipal** und **GenericIdentity** veranschaulicht.  Der Code zeigt die Werte dieser Objekte in der Konsole an.  
  
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
  
 Bei der Ausführung zeigt die Anwendung folgende Ausgabe an.  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## Siehe auch  
 <xref:System.Security.Principal.GenericIdentity>   
 <xref:System.Security.Principal.GenericPrincipal>   
 <xref:System.Security.Permissions.PrincipalPermission>   
 [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md)   
 [Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md)