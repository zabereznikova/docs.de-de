---
title: "Hinzufügen eines Dienstverweises in einer Workflowprojektmappe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 511ff8fa982e9a9ca29faf714725626f7925f659
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Hinzufügen eines Dienstverweises in einer Workflowprojektmappe
Die Abläufe beim Hinzufügen eines Dienstverweises in einer Workflowanwendung unterscheiden sich geringfügig von denen bei einer standardmäßigen WCF-Anwendung. Wenn Sie "Dienstverweis hinzufügen" auswählen und die URL des Diensts angeben, werden die Metadaten heruntergeladen, und es werden benutzerdefinierte Aktivitäten generiert, die das Aufrufen des WCF-Diensts oder WCF-Workflowdiensts ermöglichen, dem Sie einen Verweis hinzugefügt haben. Nach dem Hinzufügen eines Dienstverweises erstellen Sie die Projektmappe erneut, damit die generierten Aktivitäten erstellt werden. Die Aktivitäten werden in der Toolbox des Workflow-Designers angezeigt. Diese Vorgehensweise funktioniert jedoch nur, wenn Sie einen Dienstverweis innerhalb einer Workflowprojektmappe erstellen. Die folgenden Webcast wird gezeigt, wie das Hinzufügen eines Dienstverweises in anderen Projekttypen: [Aufrufen eines WCF-Diensts aus einem Workflow in einem Webprojekt](http://go.microsoft.com/fwlink/?LinkId=207725).  
  
 Wenn Sie Diensten, die denselben Vorgangsnamen enthalten, zwei oder mehrere Dienstverweise hinzufügen, führt dies zu einem Problem. Die generierten Aktivitäten rufen nur den ersten Dienstvorgang auf. Sie können dieses Problem umgehen, indem Sie die Dienstvorgänge entsprechend umbenennen oder den Namen der Endpunktkonfiguration in jeder generierten Aktivität ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Vorgehensweise: Erstellen eines Workflowdiensts, das Aufrufen eines anderen Workflowdiensts](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 [Aufrufen eines WCF-Diensts aus einem Workflow in einem Webprojekt](http://go.microsoft.com/fwlink/?LinkId=207725)
