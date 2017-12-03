---
title: "Einschränkungstypen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd73776aebb571fad732f554d6a96c1611506e8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`