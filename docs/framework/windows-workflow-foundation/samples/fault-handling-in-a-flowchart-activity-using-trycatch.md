---
title: Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 42eb660aff01c7e29227c28a6ad0d47d4370eb91
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016015"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch

In diesem Beispiel wird gezeigt, wie die <xref:System.Activities.Statements.TryCatch>-Aktivität innerhalb einer komplexen Ablaufsteuerungsaktivität verwendet werden kann.

In diesem Beispiel werden ein Promotionscode und eine Anzahl von Kindern als Variablen an eine <xref:System.Activities.Statements.Flowchart>-Aktivität übergeben, die einen Rabatt auf Grundlage von Formeln berechnet, die dem Promotioncode entsprechen. Zum Beispiel gehören obligatorischer Code und Workflow-Designer-Versionen des Beispiels.

In der folgenden Tabelle werden die Variablen für die `CreateFlowchartWithFaults`-Aktivität aufgelistet.

|Parameter|Beschreibung|
|----------------|-----------------|
|promoCode|Der Promotionscode. Typ: Zeichenfolge<br /><br /> Die möglichen Werte mit einer Beschreibung in Klammern:<br /><br /> -Single (Single)<br />-MNK (ohne Kinder verheiratet)<br />-MWK (mit Kindern verheiratet)|
|numKids|Die Anzahl der Kinder. Typ: int|

Die `CreateFlowchartWithFaults`-Aktivität verwendet eine <xref:System.Activities.Statements.FlowSwitch%601>-Aktivität, die auf das `promoCode`-Argument umschaltet und den Rabatt mit der folgenden Formel berechnet.

|Wert von `promoCode`|Rabatt (%)|
|--------------------------|--------------------|
|Single|10|
|MNK|15|
|MWK|15 + (1 – 1/`numberOfKids`)\*10 **Hinweis:**  Potenziell kann diese Berechnung eine <xref:System.DivideByZeroException> auslösen. Deshalb wird die Rabattberechnung in eine <xref:System.Activities.Statements.TryCatch>-Aktivität eingeschlossen, die die <xref:System.DivideByZeroException>-Ausnahme abfängt und den Rabatt auf 0 (null) festlegt.|

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2010 die Projektmappendatei flowchartwithfaulthandult. sln.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Drücken Sie F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a>Siehe auch

- [Flussdiagrammworkflows](../flowchart-workflows.md)
- [Ausnahmen](../exceptions.md)
