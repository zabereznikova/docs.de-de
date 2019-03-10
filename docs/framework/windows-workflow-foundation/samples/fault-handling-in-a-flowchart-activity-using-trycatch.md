---
title: Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 3f45d4a60de3201a3100fba3af6cc15484a1fbf0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708833"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch
In diesem Beispiel wird gezeigt, wie die <xref:System.Activities.Statements.TryCatch>-Aktivität innerhalb einer komplexen Ablaufsteuerungsaktivität verwendet werden kann.

 In diesem Beispiel werden ein Promotionscode und eine Anzahl von Kindern als Variablen an eine <xref:System.Activities.Statements.Flowchart>-Aktivität übergeben, die einen Rabatt auf Grundlage von Formeln berechnet, die dem Promotioncode entsprechen. Zum Beispiel gehören obligatorischer Code und Workflow-Designer-Versionen des Beispiels.

 In der folgenden Tabelle werden die Variablen für die `CreateFlowchartWithFaults`-Aktivität aufgelistet.

|Parameter|Beschreibung|
|----------------|-----------------|
|promoCode|Der Promotionscode. Typ: Zeichenfolge<br /><br /> Die möglichen Werte mit einer Beschreibung in Klammern:<br /><br /> – Einzelne (einfach)<br />-MNK (Verheiratet ohne Kinder).<br />-MWK (Verheiratet mit Kindern).|
|numKids|Die Anzahl der Kinder. Typ: int|

 Die `CreateFlowchartWithFaults`-Aktivität verwendet eine <xref:System.Activities.Statements.FlowSwitch%601>-Aktivität, die auf das `promoCode`-Argument umschaltet und den Rabatt mit der folgenden Formel berechnet.

|Wert von `promoCode`|Rabatt (%)|
|--------------------------|--------------------|
|Single|10|
|MNK|15|
|MWK|15 + (1 – 1 /`numberOfKids`)\*10 **beachten:**  Potenziell kann diese Berechnung eine <xref:System.DivideByZeroException> auslösen. Deshalb wird die Rabattberechnung in eine <xref:System.Activities.Statements.TryCatch>-Aktivität eingeschlossen, die die <xref:System.DivideByZeroException>-Ausnahme abfängt und den Rabatt auf 0 (null) festlegt.|

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1.  Öffnen Sie die Projektmappendatei "flowchartwithfaulthandling.sln" mit Visual Studio 2010.

2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3.  Drücken Sie F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>Siehe auch
- [Flussdiagrammworkflows](../flowchart-workflows.md)
- [Ausnahmen](../exceptions.md)
