---
title: "Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41a5d5645f66f69fd267b75359d0c74952b7b4bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner
In diesem Beispiel wird gezeigt, wie das <xref:System.Activities.Presentation.View.ExpressionTextBox> in einem benutzerdefinierten Aktivitätsdesigner verwendet wird. Die benutzerdefinierte Aktivität, `MultiAssign`, weist zwei Zeichenfolgenvariablen zwei Zeichenfolgenwerten zu. Einige <xref:System.Activities.Presentation.View.ExpressionTextBox>-Steuerelemente werden an <xref:System.Activities.InArgument>e gebunden, und einige werden an <xref:System.Activities.OutArgument>e gebunden.  
  
## <a name="sample-details"></a>Beispieldetails  
 Der `ArgumentToExpressionConverter` ist der verwendete Typkonverter, wenn Bindungsausdrücke an Argumente gebunden werden. `ConverterParameter` muss ggf. auf `In` oder `Out` festgelegt werden. `InOut` wird nicht unterstützt.  
  
 Die `UseLocationExpression` Attribut wird verwendet, auf `OutArgument`s, um anzugeben, dass der Ausdruck einen Ausdruck ein L-Wert ("Linker Wert" oder "Location-Wert") werden soll. In den meisten Fällen ist ein L-Wert-Ausdruck ein gültiger Visual Basic-Bezeichner, der verwendet wird, um anzugeben, dass das zurückgegebene `OutArgument` eine Variable oder ein Argumentname ist.  
  
 Das `MaxLines`-Attribut wird in diesem Beispiel auf 1 festgelegt, und `MinLines` wird nicht festgelegt. Dadurch wird angegeben, dass das <xref:System.Activities.Presentation.View.ExpressionTextBox> eine feste Größe von einer Zeile hat, unabhängig von der Menge von Text, die vom Benutzer eingegeben wird. Damit das <xref:System.Activities.Presentation.View.ExpressionTextBox> an die Benutzereingabe angepasst werden kann, legen Sie `MaxLines` größer als `MinLines` fest.  
  
 Ein ExpressionTextBox kann nur an Argumente gebunden werden und nicht an CLR-Eigenschaften.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei "ExpressionTextBoxSample.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
#### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus  
  
1.  Fügen Sie der Projektmappe eine neue Konsolenanwendung für Workflows hinzu.  
  
2.  Hinzufügen eines Verweises auf die **ExpressionTextBoxSample** Projekt aus der neue Workflow-Konsolenanwendungsprojekt.  
  
3.  Erstellen Sie die Projektmappe.  
  
4.  Ziehen Sie die **MultiAssign** Aktivität aus der Toolbox, und legen Sie sie in den Workflow.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [Entwickeln von Anwendungen mit dem Workflow-Designer](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
