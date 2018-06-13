---
title: Einschränkungstypen
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 53e5975017c3a27ede8ad07cd93f78f71df2d3e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517507"
---
# <a name="constraint-types"></a>Einschränkungstypen
In diesem Beispiel werden zwei verschiedene Möglichkeiten zum Anwenden von Einschränkungen auf einen Workflow veranschaulicht. Eine Möglichkeit besteht darin, dies innerhalb der Aktivität auszuführen (Build), die andere Möglichkeit besteht darin, dies außerhalb der Aktivität auszuführen (Richtlinie). In diesem Szenario möchte ein Aktivitätsautor (von einem Drittanbieter-Softwareunternehmen) die Beziehung zwischen zwei Argumenten überprüfen. In diesem Fall sollten die Kosten kleiner oder gleich dem Preis sein. Dies ist eine allgemeine Validierungsbuildeinschränkung.  
  
 Dann möchte ein Geschäftsbesitzer dieser generischen Aktivität eine Validierung hinzufügen. Der Großteil der Produkte soll 9,99 Euro oder weniger kosten. Deshalb verwendet er eine Richtlinieneinschränkung, die auf der `CreateProduct`-Aktivität basiert.  
  
 Im Beispiel:  
  
 Der Aktivitätsautor (Build) muss Folgendes tun:  
  
-   Eine Einschränkung erstellen (`PriceGreaterThanCost`). An dieser Stelle befindet sich die Validierungslogik.  
  
-   Die `System.Activities.CodeActivity.OnGetConstraints()` überschreiben und die Einschränkung (`PriceGreaterThanCost`) den Einschränkungen <xref:System.Collections.IList> hinzufügen.  
  
 Der Workflowautor (Richtlinie) muss Folgendes tun:  
  
-   Einen Workflow mit einer Instanz der Aktivität erstellen, um (`CreateProduct`) zu überprüfen.  
  
-   Eine Einschränkung erstellen (`MaxPrice`).  
  
-   Eine Instanz von <xref:System.Activities.Validation.ValidationSettings> erstellen (`validationSettings`) und die Einschränkung (`MaxPrice`) der Auflistung `AdditionalConstraints` hinzufügen. Hier kann der Workflowautor jeder Aktivität, z. B. einer Sequenz oder Parallele, Richtlinieneinschränkungen hinzufügen.  
  
-   <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufrufen, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.ValidationError>-Objekten zurückgegeben wird.  
  
-   (Optional) Die <xref:System.Activities.Validation.ValidationError>-Objekte drucken.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Beispielprojektmappe ConstraintTypes.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`