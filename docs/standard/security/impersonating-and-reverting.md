---
title: Wechseln und Zurücksetzen der Identität
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET Framework], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 14b01ec3ac800abd795e87b641a442df100f102b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706018"
---
# <a name="impersonating-and-reverting"></a>Wechseln und Zurücksetzen der Identität
Es kann vorkommen, dass Sie das Token eines Windows-Kontos abrufen müssen, um die Identität eines Windows-Kontos zu wechseln. Beispielsweise könnte es sein, dass Ihre ASP.NET-basierte Anwendung im Namen unterschiedlicher Benutzer zu unterschiedlichen Zeiten Aktionen ausführen muss. Ihre Anwendung kann hierzu von Internetinformationsdienste (IIS) ein Token akzeptieren, das einem Administrator entspricht, die Identität dieses Benutzers annehmen, einen Vorgang ausführen und zur vorherigen Identität zurückkehren. Anschließend kann die Anwendung ein Token von IIS akzeptieren, das einem Benutzer mit weniger Rechten entspricht, einige Vorgänge ausführen und die Identität erneut zurücksetzen.  
  
 In Fällen, in denen Ihre Anwendung die Identität eines Windows-Kontos annehmen muss, das von IIS nicht an den aktuellen Thread angefügt wurde, müssen Sie das Token dieses Kontos abrufen und mit ihm das Konto aktivieren. Führen Sie dazu die folgenden Aufgaben aus:  
  
1. Rufen Sie ein Kontotoken für einen bestimmten Benutzer ab, indem Sie die nicht verwaltete **LogonUser**-Methode aufrufen. Diese Methode befindet sich nicht in der .NET Framework-Basisklassenbibliothek, sondern in der nicht verwalteten **advapi32.dll**. Der Zugriff auf Methoden in nicht verwaltetem Code ist ein weitergehender Vorgang und liegt außerhalb des Rahmens dieser Erörterung. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../docs/framework/interop/index.md). Weitere Informationen zur **LogonUser**-Methode und zu **advapi32.dll** finden Sie in der Platform SDK-Dokumentation.  
  
2. Erstellen Sie eine neue Instanz der **WindowsIdentity**-Klasse, und übergeben Sie dabei das Token. Der folgende Code veranschaulicht diesen Aufruf, wobei `hToken` einem Windows-Token entspricht.  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. Beginnen Sie mit dem Identitätswechsel, indem Sie eine neue Instanz der <xref:System.Security.Principal.WindowsImpersonationContext>-Klasse erzeugen und diese, wie im folgenden Code dargestellt, mit der <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType>-Methode der initialisierten Klasse initialisieren.  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. Wenn Sie die neue Identität nicht mehr benötigen, rufen Sie die <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType>-Methode auf, um den Identitätswechsel zurückzunehmen, wie im folgenden Code gezeigt.  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 Wenn vertrauenswürdiger Code bereits ein <xref:System.Security.Principal.WindowsPrincipal> Objekt an den Thread angefügt **hat, können**Sie die Instanzmethode Identität annehmen, die kein Konto Token übernimmt. Dies ist aber nur sinnvoll, wenn das **WindowsPrincipal**-Objekt im Thread einem Benutzer entspricht, der nicht der Benutzer ist, für den der Prozess derzeit ausgeführt wird. Diese Situation kann z. B. gegeben sein, wenn Sie ASP.NET mit aktivierter Windows-Authentifizierung und deaktiviertem Identitätswechsel verwenden. In diesem Fall wird der Prozess unter einem in Internetinformationsdienste (IIS) konfigurierten Konto ausgeführt, während der aktuelle Prinzipal dem Windows-Benutzer entspricht, der auf die Seite zugreift.  
  
 Beachten Sie, **dass weder Identitäts** Wechsel noch **Rückgängig** das **Prinzipal** Objekt (<xref:System.Security.Principal.IPrincipal>) ändert, das dem aktuellen-Kontext zugeordnet ist. Stattdessen wird sowohl beim Annehmen einer Identität als auch beim Zurücksetzen das Token geändert, das dem aktuellen Betriebssystemprozess zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [Principal- und Identitätsobjekte](../../../docs/standard/security/principal-and-identity-objects.md)
- [Interoperabilität mit nicht verwaltetem Code](../../../docs/framework/interop/index.md)
