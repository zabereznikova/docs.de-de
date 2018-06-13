---
title: Benutzerdefinierte Aktivität „Hello World“
ms.date: 03/30/2017
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
ms.openlocfilehash: 35ae5933515b3280b0d8d95157c8dd5f40f7b320
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515838"
---
# <a name="hello-world-custom-activity"></a>Benutzerdefinierte Aktivität „Hello World“
Dieses Beispiel zeigt mehrere Hauptfunktionen von Windows Workflow Foundation (WF), einschließlich Informationen zum Erstellen einer einfachen benutzerdefinierten Aktivität. Einige der Funktionen, die in diesem Beispiel veranschaulicht werden, erstellen eine benutzerdefinierte Aktivität in C# und verwenden `in`-Argumente und `out`-Argumente (<xref:System.Activities.InArgument> und <xref:System.Activities.OutArgument>).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a>Erstellen eines Workflows in Code  
 In diesem Beispiel werden zwei benutzerdefinierte Aktivitäten mit C#-Code erstellt. Beide benutzerdefinierten Aktivitäten erben direkt oder indirekt von <xref:System.Activities.Activity%601>, um einen einzelnen Wert zurückzugeben. Der Vorteil der Verwendung des generischen Rückgabewerts, statt von der nicht generischen <xref:System.Activities.Activity>-Klasse zu erben, ist, dass einige Aktivitäten (z. B. <xref:System.Activities.Statements.Assign>) in der Lage sind, auf den Rückgabewert zuzugreifen, wenn sie als Teil einer zusammengesetzten Aktivität verwendet werden.  
  
 AppendString  
 Diese Aktivität erbt von <xref:System.Activities.Activity%601> und verwendet eine <xref:System.Activities.Statements.Assign>-Aktivität, die zwei Zeichenfolgen verkettet.  
  
 PrependString  
 Diese Aktivität erbt direkt von <xref:System.Activities.CodeActivity%601> und erstellt eine ähnliche Funktionalität wie die `AppendString`-Aktivität, die in Code implementierte Logik verwendet, und nicht aus einer bereits vorhandenen Aktivität zusammengesetzt wird.  
  
 Die folgenden Dateien sind in diesem Projekt enthalten.  
  
 AppendString.cs  
 Die benutzerdefinierte Aktivität, die Zeichenfolgen zusammenfügt. Sie nimmt eine Zeichenfolge und kombiniert sie mit einer literalen Textzeichenfolge "Hello World sagt", sodass eine vollständige Meldung als Ausgabe.  
  
 PrependString.cs  
 Diese Aktivität stellt einer Eingabezeichenfolge eine vordefinierte Zeichenfolge voran.  
  
 Sequence1.xaml  
 Ein Workflow, der die benutzerdefinierten Aktivitäten `AppendString` und `PrependString` verwendet.  
  
 Program.cs  
 Ein Programm, das den Workflow ausführt.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "HelloWorld.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.