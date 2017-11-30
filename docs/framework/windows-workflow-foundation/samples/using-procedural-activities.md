---
title: "Verwenden von Verfahrensaktivitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 05b4dc09ee1301366c95b447d767219460c46f99
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="using-procedural-activities"></a><span data-ttu-id="983d3-102">Verwenden von Verfahrensaktivitäten</span><span class="sxs-lookup"><span data-stu-id="983d3-102">Using Procedural Activities</span></span>
<span data-ttu-id="983d3-103">Im Beispiel werden die Aktivitäten <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> und <xref:System.Activities.Statements.WriteLine> verwendet, um ein Ratespiel zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="983d3-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="983d3-104">Bei dem Ratespiel wird eine Zufallszahl ausgewählt, die der Spieler erraten muss.</span><span class="sxs-lookup"><span data-stu-id="983d3-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="983d3-105">Wenn der Spieler die falsche Zahl eingibt, stellt der Workflow einen Hinweis bereit, ob die zu erratende Zahl höher oder niedriger ist.</span><span class="sxs-lookup"><span data-stu-id="983d3-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="983d3-106">Wenn der Spieler die Zahl in weniger als sieben Versuchen errät, wird eine Glückwunschmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="983d3-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="983d3-107">Benutzerdefinierte Aktivitäten in diesem Beispiel</span><span class="sxs-lookup"><span data-stu-id="983d3-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="983d3-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="983d3-108">ReadLine</span></span>  
 <span data-ttu-id="983d3-109">Liest eine Textzeile aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="983d3-109">Reads a line of text from the console.</span></span> <span data-ttu-id="983d3-110">Diese Aktivität ist von der <xref:System.Activities.NativeActivity>-Klasse abgeleitet und erstellt ein Lesezeichen zur Wiederaufnahme durch die Konsolenanwendung nach dem Lesen einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="983d3-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="983d3-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="983d3-111">PromptInt</span></span>  
 <span data-ttu-id="983d3-112">Fordert den Benutzer auf, eine Zahl einzugeben, und liest diese aus einem Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="983d3-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="983d3-113">Die Aktivität ist von <xref:System.Activities.Activity%601> abgeleitet und verwendet die <xref:System.Activities.Statements.WriteLine>-Aktivität und die `ReadLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="983d3-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="983d3-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="983d3-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="983d3-115">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "GuessingGame.sln".</span><span class="sxs-lookup"><span data-stu-id="983d3-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="983d3-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="983d3-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="983d3-117">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="983d3-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="983d3-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="983d3-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="983d3-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="983d3-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="983d3-120">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="983d3-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="983d3-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="983d3-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`