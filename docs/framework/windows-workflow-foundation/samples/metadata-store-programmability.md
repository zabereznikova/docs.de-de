---
title: Programmierbarkeit des Metadatenspeichers
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b38aec2e3f06e1f998bbc042c70909d208d3b63
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="metadata-store-programmability"></a>Programmierbarkeit des Metadatenspeichers
Der Metadatenspeicher ist eine [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]-Funktion, die zur Laufzeit die Zuordnung beliebiger Metadaten in Form von CLR-Attributen zu Typen zulässt. Dies ermöglicht eine lose Kopplung zwischen den Laufzeitkomponenten und ihren Entwurfszeitäquivalenten sowie die Fähigkeit, die Entwurfszeitkomponenten ohne Einfluss auf die Laufzeit zu ändern. Das Bespiel zeigt, wie eine Programmierung mit dem Metadatenspeicher durch Anwenden von Attributen auf einen Laufzeittyp, dessen Quelle nicht gesteuert werden kann, durchgeführt werden kann. Die in der Regel verwendete Terminologie ist, dass eine Hostinganwendung die Metadaten für einen Satz von Typen registriert.  
  
 In der Ausgabe möglicherweise haben Sie bemerkt ein zusätzliches, Unerwartetes Attribut <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`. Es wird beim Verwenden der Metadaten-API hinzugefügt und hat keine Auswirkungen auf das Ausführen des Beispiels.  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
## <a name="demonstrates"></a>Veranschaulicht  
  
-   Attributeinfügung mit der Metadatenspeicher-API.  
  
-   Verzögern der Metadatenregistrierung mithilfe eines Rückrufmechanismus.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ProgrammingMetadataStore.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`