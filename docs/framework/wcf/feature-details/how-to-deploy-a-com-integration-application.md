---
title: 'Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aca9df2be74dba308d3c4e4eb1c61b3e1afaa580
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-deploy-a-com-integration-application"></a>Vorgehensweise: Bereitstellung einer COM+-Integrationsanwendung
Sobald Sie eine COM+-Integrationsanwendung geschrieben haben, möchten Sie diese auf einem anderen Computer bereitstellen. In diesem Thema wird beschrieben, wie eine COM+-Integrationsanwendung von einem Computer auf einen anderen verschoben wird.  
  
### <a name="moving-a-com-hosted-integration-app"></a>Verschieben einer COM+-gehosteten Integrationsanwendung  
  
1.  Stellen Sie sicher, dass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auf beiden Computern installiert ist.  
  
2.  Exportieren Sie die Anwendung von Computer A.  
  
3.  Importieren Sie die Anwendung auf Computer B.  
  
4.  Richten Sie das Stammverzeichnis der Anwendung ein. Gemäß der Konventionen ist dies %PROGRAMFILES%/ComPlus Applications/{AppGUID}.  
  
5.  Kopieren Sie die Dateien Application.config und Application.manifest aus dem Stammverzeichnis der Anwendung auf dem Computer A in das Stammverzeichnis der Anwendung auf dem Computer B.  
  
6.  Bearbeiten Sie die Adressen der Dienstendpunkte in der Datei Application.config auf Computer B, um den entsprechenden Computer zu identifizieren. Beispiel: Ändern Sie http://machineA/MyService in http://machineB/MyService.  
  
### <a name="moving-a-web-hosted-integration-application"></a>Verschieben einer im Internet gehosteten Integrationsanwendung  
  
1.  Stellen Sie sicher, dass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auf beiden Computern installiert ist.  
  
2.  Exportieren Sie die Anwendung von Computer A.  
  
3.  Importieren Sie die Anwendung auf Computer B.  
  
4.  Erstellen Sie einen IIS-vroot auf Computer B.  
  
5.  Kopieren Sie die .svc-Datei (Komponentenname.svc) und die Datei Web.config vom vroot auf dem Computer A in das neu erstellte vroot auf Computer B.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Integration von COM+-Anwendungen](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
