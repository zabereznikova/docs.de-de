---
title: Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 6d3df9e18c7239f0e4695509d80edfd02e9a9d6f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182765"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner
In diesem Beispiel wird gezeigt, wie das <xref:System.Activities.Presentation.View.ExpressionTextBox> in einem benutzerdefinierten Aktivitätsdesigner verwendet wird. Die benutzerdefinierte Aktivität, `MultiAssign`, weist zwei Zeichenfolgenvariablen zwei Zeichenfolgenwerten zu. Einige <xref:System.Activities.Presentation.View.ExpressionTextBox>-Steuerelemente werden an <xref:System.Activities.InArgument>e gebunden, und einige werden an <xref:System.Activities.OutArgument>e gebunden.

## <a name="sample-details"></a>Beispieldetails
 Der `ArgumentToExpressionConverter` ist der verwendete Typkonverter, wenn Bindungsausdrücke an Argumente gebunden werden. `ConverterParameter` muss ggf. auf `In` oder `Out` festgelegt werden. `InOut` wird nicht unterstützt.

 Das `UseLocationExpression` Attribut wird `OutArgument`auf s verwendet, um anzugeben, dass der Ausdruck ein L-Wert-Ausdruck ("linker Wert" oder "Standortwert") sein soll. In den meisten Fällen ist ein L-Wert-Ausdruck ein gültiger Visual Basic-Bezeichner, der verwendet wird, um anzugeben, dass das zurückgegebene `OutArgument` eine Variable oder ein Argumentname ist.

 Das `MaxLines`-Attribut wird in diesem Beispiel auf 1 festgelegt, und `MinLines` wird nicht festgelegt. Dadurch wird angegeben, dass das <xref:System.Activities.Presentation.View.ExpressionTextBox> eine feste Größe von einer Zeile hat, unabhängig von der Menge von Text, die vom Benutzer eingegeben wird. Damit das <xref:System.Activities.Presentation.View.ExpressionTextBox> an die Benutzereingabe angepasst werden kann, legen Sie `MaxLines` größer als `MinLines` fest.

 Ein ExpressionTextBox kann nur an Argumente gebunden werden und nicht an CLR-Eigenschaften.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2010 die Datei ExpressionTextBoxSample.sln.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

#### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus

1. Fügen Sie der Projektmappe eine neue Konsolenanwendung für Workflows hinzu.

2. Fügen Sie einen Verweis auf das **ExpressionTextBoxSample-Projekt** aus dem neuen Workflow Console Application-Projekt hinzu.

3. Erstellen Sie die Projektmappe.

4. Ziehen Sie die **MultiAssign-Aktivität** aus der Toolbox, und legen Sie sie in den Workflow ab.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [Entwickeln von Anwendungen mit dem Workflow-Designer](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
