---
title: Beispiel für Workflowsuche
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: b3a2d88028f3854746d4e1d2fad80aae4f6be7be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143485"
---
# <a name="workflow-discovery-sample"></a>Beispiel für Workflowsuche
Dieses Beispiel veranschaulicht, wie ein Workflowdienst erkennbar gemacht wird, und wie eine benutzerdefinierte Codeaktivität erstellt wird, die nach einem bestimmten Dienst sucht.  
  
## <a name="demonstrates"></a>Zeigt  
 Suchaktivität und Workflowverwendung  
  
## <a name="discussion"></a>Diskussion  
 Im ersten Teil des Beispiels wird ein Workflowdienst mithilfe der Konfiguration erkennbar gemacht. Die Konfiguration kann auch verwendet werden, um den Dienst mit benutzerdefinierten Metadaten (z. B. Bereiche) ordnungsgemäß anzuwenden. Im Beispiel wird eine benutzerdefinierte Codeaktivität für den Client verwendet, die mit dem Suchdienst nach einem Dienst sucht, der mit einem bestimmten Vertrag übereinstimmt. Die Codeaktivität gibt einen URI aus, der später von einer Sendeaktivität verwendet wird.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. In diesem Beispiel werden HTTP-Endpunkte verwendet, für die die Ausführung über die richtigen URL-ACLs verfügen muss (Details finden Sie unter [Konfigurieren von HTTP und HTTPS).](../feature-details/configuring-http-and-https.md) Wenn der folgende Befehl an einer Eingabeaufforderung auf höherer Ebene ausgeführt wird, sollten die entsprechenden ACLs hinzugefügt werden. Wenn Ihre Shell das Variablenformat nicht versteht, ersetzen Sie Ihre Domäne und Ihren Benutzernamen durch die folgenden Argumente.  
  
     **netsh http urlaclhttp://+:8000/ url= user=%DOMAIN%\\%UserName%**  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
