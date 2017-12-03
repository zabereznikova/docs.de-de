---
title: Dynamische Argumente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 122ad479-d306-4602-a943-5aefe711329d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 582f8815bd121199e564af7d1806f2e76f4595cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="dynamic-arguments"></a>Dynamische Argumente
In diesem Beispiel wird veranschaulicht, wie eine Aktivität implementiert wird, deren Argumente statt vom Autor vom Consumer der Aktivität definiert werden. Hierzu wird die Methode überschrieben, mit der die Laufzeit die Metadaten der Aktivität erstellt.  
  
## <a name="sample-details"></a>Beispieldetails  
 Vor der Ausführung erstellt die Laufzeit die Beschreibung einer Aktivität, indem die öffentlichen Member des Aktivitätstyps analysiert und Argumente, Variablen, untergeordnete Aktivitäten und Aktivitätsdelegaten als Teil der Aktivitätsmetadaten deklariert werden. Dies dient der Sicherstellung der korrekten Workflowerstellung sowie der Verwaltung von Laufzeitbeziehungen und Lebensdauerregeln. In der Regel werden die Argumente einer Aktivität vom Aktivitätsautor durch Angabe von öffentlichen Membern des Aktivitätstyps definiert, die von <xref:System.Activities.Argument> abgeleitet werden. Für jeden von <xref:System.Activities.Argument> abgeleiteten öffentlichen Member erstellt die Laufzeit ein <xref:System.Activities.RuntimeArgument> und bindet dieses an das vom Benutzer bereitgestellte Argument für diesen Member. In einigen Fällen jedoch stellt der Consumer der Aktivität Konfigurationswerte bereit, die den Satz der Argumente bestimmen. Ein Aktivitätsautor überschreibt <xref:System.Activities.Activity.CacheMetadata%2A>, um die Methode zur Erstellung von Aktivitätsmetadaten anzupassen, darunter auch der mit der Aktivität verknüpfte Satz von Argumenten.  
  
 In diesem Beispiel wird veranschaulicht, wie eine Argumentliste für eine Aktivität, die eine Methode aufruft, dynamisch erstellt wird. Der Consumer der Aktivität gibt den Typ und den Namen der Methode an, die aufgerufen werden soll, sowie eine Auflistung von Argumenten, die an diese Methode übergeben werden sollen.  
  
> [!NOTE]
>  Anhand dieses Beispiels wird veranschaulicht, wie <xref:System.Activities.CodeActivity.CacheMetadata%2A> überschrieben wird und wie <xref:System.Activities.RuntimeArgument> verwendet wird. Hinsichtlich der Arten von Methoden, die mit dieser Aktivität aufgerufen werden können, sind mehrere Einschränkungen zu beachten. Sie funktioniert beispielsweise nicht mit Generika oder Parameterarrays. Diese und andere Fälle werden mit der im Lieferumfang von .NET Framework enthaltenen <xref:System.Activities.Statements.InvokeMethod>-Aktivität behandelt.  
  
 Die `MethodInvoke`-Aktivität überschreibt <xref:System.Activities.CodeActivity.CacheMetadata%2A> und beginnt mit der Erstellung eines <xref:System.Activities.RuntimeArgument>-Elements zur Behandlung der Ergebnisse des Methodenaufrufs. Sie bindet dieses <xref:System.Activities.RuntimeArgument> an das öffentlich einstellbare <xref:System.Activities.OutArgument> mit dem Namen `Result`. Wenn `MethodInvoke.Result` den Wert `null` aufweist, fügt die Laufzeit automatisch ein mit dem Standardausdruck für diesen Typ konfiguriertes <xref:System.Activities.OutArgument> ein. Auf diese Weise muss der Autor einer Aktivität nicht prüfen, ob die Eigenschaft eines Arguments `null` ist.  
  
 Als Nächstes ermittelt die <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung das für den Aufruf verwendete `MethodInfo`-Element anhand des vom Benutzer bereitgestellten `MethodName` und `TargetType`. Die `DetermineMethodInfo`-Methode verwendet den an die <xref:System.Activities.CodeActivityMetadata>-Überschreibung übergebenen <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Parameter, sodass alle Konfigurationsfehler als Validierungsfehler gemeldet werden können. Hierzu wird `metadata.AddValidationError` aufgerufen.  
  
 Nachdem das `MethodInfo`-Element festgelegt wurde, werden die `MethodInfo`-Parameter durchlaufen. Für jeden Parameter wird ein <xref:System.Activities.RuntimeArgument> erstellt und an das entsprechende Argument in der vom Benutzer bereitgestellten Auflistung der `Parameters`-Eigenschaft gebunden. Zum Schluss wird die <xref:System.Activities.RuntimeArgument>-Auflistung durch Aufruf von `metadata.SetArgumentsCollection` der Aktivität zugeordnet.  
  
 Beachten Sie, dass zur Argumentauflösung ein <xref:System.Activities.RuntimeArgument> (wie im Fall von `resultArgument`) oder ein vom Benutzer bereitgestelltes Argument (wie im Fall der `Parameters`-Auflistung) verwendet werden kann.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Datei "DynamicArguments.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\DynamicArguments`