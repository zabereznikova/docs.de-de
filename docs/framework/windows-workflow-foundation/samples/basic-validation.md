---
title: Grundlegende Validierung
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408328"
---
# <a name="basic-validation"></a>Grundlegende Validierung
Dieses Beispiel besteht aus einer Aktivität, `CreateProduct`, die überprüft, ob ihr `Cost`-Argument kleiner oder gleich ihrem `Price`-Argument ist.  
  
## <a name="sample-details"></a>Beispieldetails  
 Es gibt zwei Autoren, die die Validierung verwenden, den Aktivitätsautor (erstellt die Validierungslogik für die Aktivität) und den Workflowautor, der Validierungsdienste in einem bestimmten Workflow aufruft. In diesem Szenario möchte der Aktivitätsautor erzwingen, dass jede Instanz seiner Aktivität kleinere oder gleiche Kosten als der Preis haben muss.  
  
 Der Aktivitätsautor (innerhalb der Aktivität) muss:  
  
-   Eine Einschränkung erstellen (`PriceGreaterThanCost`). An dieser Stelle befindet sich die Validierungslogik.  
  
-   Die `System.Activities.CodeActivity.OnGetConstraints()` überschreiben und die Einschränkung (`PriceGreaterThanCost`) den Einschränkungen <xref:System.Collections.IList> hinzufügen.  
  
 Der Workflowautor (Hauptprogramm) muss:  
  
-   Einen Workflow mit einer Instanz der Aktivität erstellen, um (`CreateProduct`) zu überprüfen.  
  
-   <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufrufen, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.ValidationError> zurückgegeben wird.  
  
-   (Optional) Die <xref:System.Activities.Validation.ValidationError>-Objekte drucken.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Projektmappe "BasicValidation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`