---
title: Programmierbarkeit des Metadatenspeichers
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 9f30fcdac131b8749a4d165875b9bbb584542843
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47209859"
---
# <a name="metadata-store-programmability"></a>Programmierbarkeit des Metadatenspeichers
Der Metadatenspeicher ist eine [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]-Funktion, die zur Laufzeit die Zuordnung beliebiger Metadaten in Form von CLR-Attributen zu Typen zulässt. Dies ermöglicht eine lose Kopplung zwischen den Laufzeitkomponenten und ihren Entwurfszeitäquivalenten sowie die Fähigkeit, die Entwurfszeitkomponenten ohne Einfluss auf die Laufzeit zu ändern. Das Bespiel zeigt, wie eine Programmierung mit dem Metadatenspeicher durch Anwenden von Attributen auf einen Laufzeittyp, dessen Quelle nicht gesteuert werden kann, durchgeführt werden kann. Die in der Regel verwendete Terminologie ist, dass eine Hostinganwendung die Metadaten für einen Satz von Typen registriert.  
  
 In der Ausgabe fällt Ihnen möglicherweise ein zusätzliches, unerwartetes Attribut auf, <xref:System.Runtime.InteropServices.GuidAttribute>. Es wird beim Verwenden der Metadaten-API hinzugefügt und hat keine Auswirkungen auf das Ausführen des Beispiels.  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
## <a name="demonstrates"></a>Veranschaulicht  
  
-   Attributeinfügung mit der Metadatenspeicher-API.  
  
-   Verzögern der Metadatenregistrierung mithilfe eines Rückrufmechanismus.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ProgrammingMetadataStore.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`