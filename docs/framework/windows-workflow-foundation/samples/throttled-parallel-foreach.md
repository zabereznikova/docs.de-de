---
title: Parallel ForEach (eingeschränkt)
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 340e4ff154b63221ec911c872a1154bdb672cf8c
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715917"
---
# <a name="throttled-parallel-foreach"></a>Parallel ForEach (eingeschränkt)

Die `ThrottleParallelForEach`-Aktivität ist der <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität ähnlich, mit der einen Ausnahme, dass sie das Einstellen eines Parallelitätsfaktors zur Einschränkung der Anzahl gleichzeitiger auszuführender Verzweigungen ermöglicht. Die `ThrottleParallelForEach`-Aktivität wird von <xref:System.Activities.NativeActivity> abgeleitet, da sie andere Aktivitäten (die untergeordneten Aktivitäten) planen muss und darauf nur über die <xref:System.Activities.NativeActivityContext>-Klasse zugegriffen werden kann.

## <a name="projects"></a>Projekte

|**ProjectName**|**Beschreibung**|**Haupt Dateien**|
|-|-|-|
|ThrottledParallelForEach|Enthält die `ThrottledParallelForEach`-Aktivität und ihren Designer.|ThrottledParallelForEach.cs<br /><br /> Die `ThrottledParallelForEach`-Aktivitätsdefinition.|
|CodeTestClient|Beispielclientanwendung, die einen Workflow mithilfe von imperativem Code mit `ThrottledParallelForEach` konfiguriert ausführt.|Program.cs<br /><br /> Definiert eine Instanz des Beispielworkflows und führt sie aus.|

## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Datei "throttledparallelforeach. sln" mithilfe von Visual Studio 2010.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Drücken Sie F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`
