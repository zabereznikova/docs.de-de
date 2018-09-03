---
title: Benutzerdefinierte Aktivität „Hello World“
ms.date: 03/30/2017
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
ms.openlocfilehash: fde745fae7470ec763b6b5030a60436a6525e3c0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43470774"
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="095d9-102">Benutzerdefinierte Aktivität „Hello World“</span><span class="sxs-lookup"><span data-stu-id="095d9-102">Hello World Custom Activity</span></span>
<span data-ttu-id="095d9-103">Dieses Beispiel zeigt mehrere wichtige Features von Windows Workflow Foundation (WF), wie Sie eine einfache benutzerdefinierte Aktivität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="095d9-103">This sample demonstrates several key features of Windows Workflow Foundation (WF), including how to create a simple custom activity.</span></span> <span data-ttu-id="095d9-104">Einige der Funktionen, die in diesem Beispiel veranschaulicht werden, erstellen eine benutzerdefinierte Aktivität in C# und verwenden `in`-Argumente und `out`-Argumente (<xref:System.Activities.InArgument> und <xref:System.Activities.OutArgument>).</span><span class="sxs-lookup"><span data-stu-id="095d9-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="095d9-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="095d9-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="095d9-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="095d9-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="095d9-107">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="095d9-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="095d9-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="095d9-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="095d9-109">Erstellen eines Workflows in Code</span><span class="sxs-lookup"><span data-stu-id="095d9-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="095d9-110">In diesem Beispiel werden zwei benutzerdefinierte Aktivitäten mit C#-Code erstellt.</span><span class="sxs-lookup"><span data-stu-id="095d9-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="095d9-111">Beide benutzerdefinierten Aktivitäten erben direkt oder indirekt von <xref:System.Activities.Activity%601>, um einen einzelnen Wert zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="095d9-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="095d9-112">Der Vorteil der Verwendung des generischen Rückgabewerts, statt von der nicht generischen <xref:System.Activities.Activity>-Klasse zu erben, ist, dass einige Aktivitäten (z. B. <xref:System.Activities.Statements.Assign>) in der Lage sind, auf den Rückgabewert zuzugreifen, wenn sie als Teil einer zusammengesetzten Aktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="095d9-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="095d9-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="095d9-113">AppendString</span></span>  
 <span data-ttu-id="095d9-114">Diese Aktivität erbt von <xref:System.Activities.Activity%601> und verwendet eine <xref:System.Activities.Statements.Assign>-Aktivität, die zwei Zeichenfolgen verkettet.</span><span class="sxs-lookup"><span data-stu-id="095d9-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="095d9-115">PrependString</span><span class="sxs-lookup"><span data-stu-id="095d9-115">Prepend String</span></span>  
 <span data-ttu-id="095d9-116">Diese Aktivität erbt direkt von <xref:System.Activities.CodeActivity%601> und erstellt eine ähnliche Funktionalität wie die `AppendString`-Aktivität, die in Code implementierte Logik verwendet, und nicht aus einer bereits vorhandenen Aktivität zusammengesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="095d9-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="095d9-117">Die folgenden Dateien sind in diesem Projekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="095d9-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="095d9-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="095d9-118">AppendString.cs</span></span>  
 <span data-ttu-id="095d9-119">Die benutzerdefinierte Aktivität, die Zeichenfolgen zusammenfügt.</span><span class="sxs-lookup"><span data-stu-id="095d9-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="095d9-120">Sie nimmt eine Zeichenfolge und kombiniert sie mit einer literalen Textzeichenfolge "Hello World sagt", sodass eine vollständige Meldung als Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="095d9-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="095d9-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="095d9-121">PrependString.cs</span></span>  
 <span data-ttu-id="095d9-122">Diese Aktivität stellt einer Eingabezeichenfolge eine vordefinierte Zeichenfolge voran.</span><span class="sxs-lookup"><span data-stu-id="095d9-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="095d9-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="095d9-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="095d9-124">Ein Workflow, der die benutzerdefinierten Aktivitäten `AppendString` und `PrependString` verwendet.</span><span class="sxs-lookup"><span data-stu-id="095d9-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="095d9-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="095d9-125">Program.cs</span></span>  
 <span data-ttu-id="095d9-126">Ein Programm, das den Workflow ausführt.</span><span class="sxs-lookup"><span data-stu-id="095d9-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="095d9-127">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="095d9-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="095d9-128">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "HelloWorld.sln".</span><span class="sxs-lookup"><span data-stu-id="095d9-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="095d9-129">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="095d9-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="095d9-130">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="095d9-130">To run the solution, press F5.</span></span>