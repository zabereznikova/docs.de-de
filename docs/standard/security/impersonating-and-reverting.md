---
title: Wechseln und Zurücksetzen der Identität
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 7eecc7d6cb3fa4cc1c1bd971d36f9d3ca47a7144
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555673"
---
# <a name="impersonating-and-reverting"></a>Wechseln und Zurücksetzen der Identität

> [!NOTE]
> Dieser Artikel bezieht sich auf Windows.
>
> Weitere Informationen zu ASP.net Core finden Sie unter [ASP.net Core Sicherheit](/aspnet/core/security/).

Es kann vorkommen, dass Sie das Token eines Windows-Kontos abrufen müssen, um die Identität eines Windows-Kontos zu wechseln. Beispielsweise könnte es sein, dass Ihre ASP.NET-basierte Anwendung im Namen unterschiedlicher Benutzer zu unterschiedlichen Zeiten Aktionen ausführen muss. Ihre Anwendung kann hierzu von Internetinformationsdienste (IIS) ein Token akzeptieren, das einem Administrator entspricht, die Identität dieses Benutzers annehmen, einen Vorgang ausführen und zur vorherigen Identität zurückkehren. Anschließend kann die Anwendung ein Token von IIS akzeptieren, das einem Benutzer mit weniger Rechten entspricht, einige Vorgänge ausführen und die Identität erneut zurücksetzen.  
  
 In Fällen, in denen Ihre Anwendung die Identität eines Windows-Kontos annehmen muss, das von IIS nicht an den aktuellen Thread angefügt wurde, müssen Sie das Token dieses Kontos abrufen und mit ihm das Konto aktivieren. Führen Sie dazu die folgenden Aufgaben aus:  
  
1. Rufen Sie ein Kontotoken für einen bestimmten Benutzer ab, indem Sie die nicht verwaltete **LogonUser**-Methode aufrufen. Diese Methode befindet sich nicht in der .net-Basisklassen Bibliothek, sondern befindet sich im nicht verwalteten **advapi32.dll**. Der Zugriff auf Methoden in nicht verwaltetem Code ist ein weitergehender Vorgang und liegt außerhalb des Rahmens dieser Erörterung. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../framework/interop/index.md). Weitere Informationen zur **LogonUser**-Methode und zu **advapi32.dll** finden Sie in der Platform SDK-Dokumentation.  
  
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
  
 Wenn vertrauenswürdiger Code bereits ein- <xref:System.Security.Principal.WindowsPrincipal> Objekt an den Thread angefügt hat, können Sie die **Impersonate**Instanzmethode als Identitätswechsel verwenden, die kein Konto Token übernimmt. Dies ist aber nur sinnvoll, wenn das **WindowsPrincipal**-Objekt im Thread einem Benutzer entspricht, der nicht der Benutzer ist, für den der Prozess derzeit ausgeführt wird. Diese Situation kann z. B. gegeben sein, wenn Sie ASP.NET mit aktivierter Windows-Authentifizierung und deaktiviertem Identitätswechsel verwenden. In diesem Fall wird der Prozess unter einem in Internetinformationsdienste (IIS) konfigurierten Konto ausgeführt, während der aktuelle Prinzipal dem Windows-Benutzer entspricht, der auf die Seite zugreift.  
  
 Beachten Sie, dass weder der Identitäts **Wechsel noch** **Rückgängig** das **Prinzipal** Objekt () ändert, das <xref:System.Security.Principal.IPrincipal> dem aktuellen-Kontext zugeordnet ist. Vielmehr ändern Identitätswechsel und Zurücksetzen das Token, das dem aktuellen Betriebssystem Prozess zugeordnet ist.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [Principal- und Identitätsobjekte](principal-and-identity-objects.md)
- [Interoperabilität mit nicht verwaltetem Code](../../framework/interop/index.md)
- [ASP.net Core Sicherheit](/aspnet/core/security/)
