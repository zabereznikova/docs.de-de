---
title: Parallel ForEach (eingeschränkt)
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 8691edb8a5a61204b187be8def553f2f06be0f0d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581861"
---
# <a name="throttled-parallel-foreach"></a>Parallel ForEach (eingeschränkt)
Die `ThrottleParallelForEach` -Aktivität ist vergleichbar mit der <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` Aktivität mit einer Ausnahme, dass können einstellen eines parallelitätsfaktors zur Einschränkung der Anzahl gleichzeitiger auszuführender Branches auszuführen. Die `ThrottleParallelForEach`-Aktivität wird von <xref:System.Activities.NativeActivity> abgeleitet, da sie andere Aktivitäten (die untergeordneten Aktivitäten) planen muss und darauf nur über die <xref:System.Activities.NativeActivityContext>-Klasse zugegriffen werden kann.

## <a name="projects"></a>Projekte

|**ProjectName**|**Beschreibung**|**Hauptdateien**|
|-|-|-|
|ThrottledParallelForEach|Enthält die `ThrottledParallelForEach`-Aktivität und ihren Designer.|ThrottledParallelForEach.cs<br /><br /> Die `ThrottledParallelForEach`-Aktivitätsdefinition.|
|CodeTestClient|Beispielclientanwendung, die einen Workflow mithilfe von imperativem Code mit `ThrottledParallelForEach` konfiguriert ausführt.|Program.cs<br /><br /> Definiert eine Instanz des Beispielworkflows und führt sie aus.|

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1.  Öffnen Sie die Datei "throttledparallelforeach.sln" in mit Visual Studio 2010.

2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3.  Drücken Sie F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`