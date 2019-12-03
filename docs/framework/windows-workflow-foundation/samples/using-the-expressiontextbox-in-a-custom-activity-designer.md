---
title: Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 6b581b42c882c12425a17b9a518f8957ca10898a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715532"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner
In diesem Beispiel wird gezeigt, wie das <xref:System.Activities.Presentation.View.ExpressionTextBox> in einem benutzerdefinierten Aktivitätsdesigner verwendet wird. Die benutzerdefinierte Aktivität, `MultiAssign`, weist zwei Zeichenfolgenvariablen zwei Zeichenfolgenwerten zu. Einige <xref:System.Activities.Presentation.View.ExpressionTextBox>-Steuerelemente werden an <xref:System.Activities.InArgument>e gebunden, und einige werden an <xref:System.Activities.OutArgument>e gebunden.

## <a name="sample-details"></a>Beispieldetails
 Der `ArgumentToExpressionConverter` ist der verwendete Typkonverter, wenn Bindungsausdrücke an Argumente gebunden werden. `ConverterParameter` muss ggf. auf `In` oder `Out` festgelegt werden. `InOut` wird nicht unterstützt.

 Das `UseLocationExpression`-Attribut wird für `OutArgument`s verwendet, um anzugeben, dass der Ausdruck ein L-Wert-Ausdruck ("Linker Wert" oder "Location Value") sein soll. In den meisten Fällen ist ein L-Wert-Ausdruck ein gültiger Visual Basic-Bezeichner, der verwendet wird, um anzugeben, dass das zurückgegebene `OutArgument` eine Variable oder ein Argumentname ist.

 Das `MaxLines`-Attribut wird in diesem Beispiel auf 1 festgelegt, und `MinLines` wird nicht festgelegt. Dadurch wird angegeben, dass das <xref:System.Activities.Presentation.View.ExpressionTextBox> eine feste Größe von einer Zeile hat, unabhängig von der Menge von Text, die vom Benutzer eingegeben wird. Damit das <xref:System.Activities.Presentation.View.ExpressionTextBox> an die Benutzereingabe angepasst werden kann, legen Sie `MaxLines` größer als `MinLines` fest.

 Ein ExpressionTextBox kann nur an Argumente gebunden werden und nicht an CLR-Eigenschaften.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2010 die Datei "expressiontextboxsample. sln".

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

#### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus

1. Fügen Sie der Projektmappe eine neue Konsolenanwendung für Workflows hinzu.

2. Fügen Sie dem Projekt " **expressiontextboxsample** " aus dem neuen Workflow Konsolen Anwendungsprojekt einen Verweis hinzu.

3. Erstellen Sie die Projektmappe.

4. Ziehen Sie die **multiassign** -Aktivität aus der Toolbox, und legen Sie Sie im Workflow ab.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [Entwickeln von Anwendungen mit dem Workflow-Designer](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
