---
title: "Grundlegende Validierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Grundlegende Validierung
Dieses Beispiel besteht aus einer Aktivität, `CreateProduct`, die überprüft, ob ihr `Cost`\-Argument kleiner oder gleich ihrem `Price`\-Argument ist.  
  
## Beispieldetails  
 Es gibt zwei Autoren, die die Validierung verwenden, den Aktivitätsautor \(erstellt die Validierungslogik für die Aktivität\) und den Workflowautor, der Validierungsdienste in einem bestimmten Workflow aufruft.In diesem Szenario möchte der Aktivitätsautor erzwingen, dass jede Instanz seiner Aktivität kleinere oder gleiche Kosten als der Preis haben muss.  
  
 Der Aktivitätsautor \(innerhalb der Aktivität\) muss:  
  
-   Eine Einschränkung erstellen \(`PriceGreaterThanCost`\).An dieser Stelle befindet sich die Validierungslogik.  
  
-   Die <xref:System.Activities.CodeActivity%601.OnGetConstraints%2A> überschreiben und die Einschränkung \(`PriceGreaterThanCost`\) den Einschränkungen <xref:System.Collections.IList> hinzufügen.  
  
 Der Workflowautor \(Hauptprogramm\) muss:  
  
-   Einen Workflow mit einer Instanz der Aktivität erstellen, um \(`CreateProduct`\) zu überprüfen.  
  
-   <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufrufen, wodurch eine <xref:System.Activities.Validation.ValidationResults>\-Auflistung von <xref:System.Activities.Validation.ConstraintViolation> zurückgegeben wird.  
  
-   \(Optional\) Die <xref:System.Activities.Validation.ConstraintViolation>\-Objekte drucken.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie die Projektmappe "BasicValidation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`  
  
## Siehe auch