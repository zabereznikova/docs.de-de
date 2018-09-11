---
title: Beispiel für Workflowsuche
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: 1076e7045ca546fed7e6902f69406bfc002c4c26
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44367781"
---
# <a name="workflow-discovery-sample"></a>Beispiel für Workflowsuche
Dieses Beispiel veranschaulicht, wie ein Workflowdienst erkennbar gemacht wird, und wie eine benutzerdefinierte Codeaktivität erstellt wird, die nach einem bestimmten Dienst sucht.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Suchaktivität und Workflowverwendung  
  
## <a name="discussion"></a>Diskussion  
 Im ersten Teil des Beispiels wird ein Workflowdienst mithilfe der Konfiguration erkennbar gemacht. Die Konfiguration kann auch verwendet werden, um den Dienst mit benutzerdefinierten Metadaten (z. B. Bereiche) ordnungsgemäß anzuwenden. Im Beispiel wird eine benutzerdefinierte Codeaktivität für den Client verwendet, die mit dem Suchdienst nach einem Dienst sucht, der mit einem bestimmten Vertrag übereinstimmt. Die Codeaktivität gibt einen URI aus, der später von einer Sendeaktivität verwendet wird.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Dieses Beispiel verwendet die HTTP-Endpunkten, die richtigen URL-ACLs ausführen müssen (finden Sie unter [Konfigurieren von HTTP und HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) Einzelheiten). Wenn der folgende Befehl an einer Eingabeaufforderung auf höherer Ebene ausgeführt wird, sollten die entsprechenden ACLs hinzugefügt werden. Ersetzen Sie die folgenden Argumente durch die Domäne und den Benutzernamen, wenn die Shell die variable Struktur nicht erkennt.  
  
     **Netsh http hinzufügen Urlacl Url =http://+:8000/ Benutzer Domäne % =\\%UserName%**  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
