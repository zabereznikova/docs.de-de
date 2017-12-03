---
title: "Warten auf Eingabeaktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d58c344e-9ee8-4ce2-b199-75b3fe45237f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d877c147a19635782b652d96031644b3be42448a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wait-for-input-activity"></a>Warten auf Eingabeaktivität
Dieses Beispiel veranschaulicht, wie benannte Lesezeichen in einem Workflow erstellt werden. [!INCLUDE[wf](../../../../includes/wf-md.md)] stellt keine Aktivität zur deklarativen Erstellung von Lesezeichen bereit. Wenn Sie daher in Ihrem Workflow ein Lesezeichen erstellen möchten, müssen Sie eine benutzerdefinierte Aktivität schreiben, die eines erstellt. Die in diesem Beispiel definierte `WaitForInput`-Aktivität stellt diese Funktionalität bereit, damit Benutzer Lesezeichen deklarativ innerhalb eines Workflows erstellen können.  
  
## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel  
  
|**Projektname**|**Beschreibung**|**Hauptdateien**|  
|-|-|-|  
|WaitForInput|Enthält die `WaitForInput`-Aktivität und ihren Designer.|WaitForInput.cs<br /><br /> Definition der `WaitForInput`-Aktivität.|  
|||WaitForInputDesigner.xaml<br /><br /> Benutzerdefinierter Designer für die `WaitForInput`-Aktivität.|  
|||TypeToFirstGenericArgumentConverter.cs<br /><br /> WPF-Typkonverter, der verwendet wird, um den generischen Typ der Aktivität im Designer zu aktualisieren.|  
|WaitForInputTestClient|Beispielclientanwendung, die mithilfe des Workflow-Designers unter Verwendung mehrerer WaitForInput-Aktivitäten einen Workflow konfiguriert und ausführt.|Sequence1.xaml<br /><br /> Ein sequenzieller Workflow, der die `WaitForInput`-Aktivität verwendet.|  
|||Program.cs<br /><br /> Führt eine Instanz des in "Sequence1.xaml" definierten Workflows aus.|  
  
## <a name="waitforinput-activity"></a>WaitForInput-Aktivität  
 Die `WaitForInput`-Aktivität erstellt in einem Workflow ein benanntes Lesezeichen. Das Lesezeichen wartet auf ein Signal und empfängt Daten von seinem konfigurierten Typ. Nachdem das Lesezeichen wiederaufgenommen wurde, sind die an den Workflow übergebenen Daten über die `Result`-Eigenschaft verfügbar.  
  
 Die `WaitForInput`-Aktivität wird von der <xref:System.Activities.NativeActivity>-Klasse abgeleitet, da sie Lesezeichen erstellen muss, auf die nur durch die <xref:System.Activities.NativeActivityContext>-Klasse zugegriffen werden kann.  
  
 Auf die Aktivität können zur Bindung an einen Designer, zum Hinzufügen der generischen Argumentfunktion, die aktualisiert werden kann, und zum Festlegen der standardmäßigen generischen Typs auf "Zeichenfolge" drei Attribute angewendet werden. Die Aktivität weist auch die in der folgenden Tabelle aufgeführten Argumente auf.  
  
|**Name**|**Typ**|**Beschreibung**|  
|-|-|-|  
|TResult|Generisches Argument (TResult)|Der Typ des Lesezeichens. Dies ist der Typ der Daten, der beim Wiederaufnehmen des Lesezeichens an das Lesezeichen übergeben werden soll.|  
|BookmarkName|InArgument\<Zeichenfolge >|Der Name des Lesezeichens.|  
|Ergebnis|InArgument\<TResult >|Die Daten, die an die Aktivität übergeben werden, wenn das Lesezeichen wiederaufgenommen wird.|  
  
## <a name="waitforinput-activity-designer"></a>WaitForInput-Aktivitätsdesigner  
 Der `WaitForInput`-Aktivitätsdesigner wird in der Datei "WaitForInputDesigner.xaml" implementiert. Die `WaitForInput`-Aktivität und ihr Designer sind in derselben Assembly enthalten. In der folgenden Abbildung ist die `WaitForInput`-Aktivität in der Toolbox innerhalb einer Kategorie dargestellt, die denselben Namen wie die Assembly hat.  
  
 ![Screenshot von WaitForInput-Toolbox](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputtoolbox.jpg "WaitForInputToolbox")  
  
 In der folgenden Abbildung ist der `WaitForInput`-Designer dargestellt. Da die `WaitForInput`-Aktivität ist sehr einfach ist, können alle Argumente im Designer direkt in der Designeroberfläche festgelegt werden.  
  
 ![WaitForInput-Aktivitätsdesigner](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputdesigner.jpg "WaitForInputDesigner")  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie Datei "WaitForInput.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um den das Beispiel zu starten.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\WaitForInput`