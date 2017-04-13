---
title: "Impersonating and Reverting | Microsoft Docs"
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
  - "WindowsIdentity objects, impersonating"
  - "security [.NET Framework], impersonating Windows accounts"
  - "impersonating Windows accounts"
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Impersonating and Reverting
Es kann vorkommen, dass Sie das Token eines Windows NT\-Kontos abrufen müssen, um die Identität eines Windows\-Kontos zu wechseln. Beispielsweise könnte es sein, dass Ihre ASP.NET\-basierte Anwendung im Namen unterschiedlicher Benutzer zu unterschiedlichen Zeiten Aktionen ausführen muss. Ihre Anwendung kann hierzu von Internetinformationsdienste \(IIS\) ein Token akzeptieren, das einem Administrator entspricht, die Identität dieses Benutzers annehmen, einen Vorgang ausführen und zur vorherigen Identität zurückkehren. Anschließend kann die Anwendung ein Token von IIS akzeptieren, das einem Benutzer mit weniger Rechten entspricht, einige Vorgänge ausführen und die Identität erneut zurücksetzen.  
  
 In Fällen, in denen Ihre Anwendung die Identität eines Windows\-Kontos annehmen muss, das von IIS nicht an den aktuellen Thread angefügt wurde, müssen Sie das Token dieses Kontos abrufen und mit ihm das Konto aktivieren. Führen Sie dazu die folgenden Schritte aus:  
  
1.  Rufen Sie ein Kontotoken für einen bestimmten Benutzer ab, indem Sie die nicht verwaltete **LogonUser**\-Methode aufrufen. Diese Methode befindet sich nicht in der .NET Framework\-Basisklassenbibliothek, sondern in der nicht verwalteten **advapi32.dll**. Der Zugriff auf Methoden in nicht verwaltetem Code ist ein weitergehender Vorgang und liegt außerhalb des Rahmens dieser Erörterung. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../docs/framework/interop/index.md). Weitere Informationen zur **LogonUser**\-Methode und zu **advapi32.dll** finden Sie in der Platform SDK\-Dokumentation.  
  
2.  Erstellen Sie eine neue Instanz der **WindowsIdentity**\-Klasse, und übergeben Sie dabei das Token. Der folgende Code veranschaulicht diesen Aufruf, wobei `hToken` einem Windows\-Token entspricht.  
  
    ```csharp  
    WindowsIdentity ImpersonatedIdentity = new WindowsIdentity(hToken);  
  
    ```  
  
    ```vb  
    Dim ImpersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3.  Beginnen Sie mit dem Identitätswechsel, indem Sie eine neue Instanz der <xref:System.Security.Principal.WindowsImpersonationContext>\-Klasse erzeugen und diese, wie im folgenden Code dargestellt, mit der <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=fullName>\-Methode der initialisierten Klasse initialisieren.  
  
    ```csharp  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate();  
  
    ```  
  
    ```vb  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate()  
    ```  
  
4.  Wenn Sie die neue Identität nicht mehr benötigen, rufen Sie die <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=fullName>\-Methode auf, um den Identitätswechsel zurückzunehmen, wie im folgenden Code gezeigt.  
  
    ```csharp  
    MyImpersonation.Undo();  
  
    ```  
  
    ```vb  
    MyImpersonation.Undo()  
    ```  
  
 Wenn vertrauenswürdiger Code bereits ein <xref:System.Security.Principal.WindowsPrincipal>\-Objekt an den Thread angefügt hat, können Sie die Instanzmethode **Impersonate** aufrufen, die kein Kontotoken übernimmt. Dies ist aber nur sinnvoll, wenn das **WindowsPrincipal**\-Objekt im Thread einem Benutzer entspricht, der nicht der Benutzer ist, für den der Prozess derzeit ausgeführt wird. Diese Situation kann z. B. gegeben sein, wenn Sie ASP.NET mit aktivierter Windows\-Authentifizierung und deaktiviertem Identitätswechsel verwenden. In diesem Fall wird der Prozess unter einem in Internetinformationsdienste \(IIS\) konfigurierten Konto ausgeführt, während der aktuelle Prinzipal dem Windows\-Benutzer entspricht, der auf die Seite zugreift.  
  
 Beachten Sie, dass weder **Impersonate** noch **Undo** das **Principal**\-Objekt \(<xref:System.Security.Principal.IPrincipal>\) ändert, das dem aktuellen Aufrufkontext zugeordnet ist. Stattdessen wird sowohl beim Annehmen einer Identität als auch beim Zurücksetzen das Token geändert, das dem aktuellen Betriebssystemprozess zugeordnet ist.  
  
## Siehe auch  
 <xref:System.Security.Principal.WindowsIdentity>   
 <xref:System.Security.Principal.WindowsImpersonationContext>   
 [Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md)   
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)