---
title: "Gewusst wie: Verhindern des Anfügens einer untergeordneten Aufgabe an die übergeordnete Aufgabe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2cab2fb9c26a8ddaa868cafebac718e5dfd6baa0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="b4c43-102">Gewusst wie: Verhindern des Anfügens einer untergeordneten Aufgabe an die übergeordnete Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b4c43-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="b4c43-103">Dieses Dokument veranschaulicht, wie das Anfügen einer untergeordneten Aufgabe an die übergeordnete Aufgabe verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="b4c43-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="b4c43-104">Sie sollten verhindern, dass eine untergeordnete Aufgabe an ihre übergeordnete Aufgabe angefügt wird, wenn Sie eine Komponente aufrufen, die von einem Drittanbieter geschrieben wurde und auch Aufgaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4c43-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="b4c43-105">So kann z.B. eine Drittanbieterkomponente bei Verwendung der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>-Option zum Erstellen eines <xref:System.Threading.Tasks.Task>- oder <xref:System.Threading.Tasks.Task%601>-Objekts Probleme im Code verursachen, wenn sie lange ausgeführt wird oder eine unbehandelte Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="b4c43-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c43-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4c43-106">Example</span></span>  
 <span data-ttu-id="b4c43-107">Im folgenden Beispiel werden die Auswirkungen der Verwendung der Standardoptionen mit den Auswirkungen verglichen, die es mit sich bringt, zu verhindern, dass eine untergeordnete Aufgabe dem übergeordneten Element angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b4c43-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="b4c43-108">Im Beispiel wird ein <xref:System.Threading.Tasks.Task>-Objekt erstellt, das einen Aufruf an eine Drittanbieterbibliothek richtet, die auch ein <xref:System.Threading.Tasks.Task>-Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4c43-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="b4c43-109">Die Drittanbieterbibliothek verwendet die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>-Option zum Erstellen des <xref:System.Threading.Tasks.Task>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b4c43-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="b4c43-110">Die Anwendung verwendet die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>-Option zum Erstellen der übergeordneten Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="b4c43-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="b4c43-111">Diese Option weist die Runtime an, die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>-Spezifikation in untergeordneten Aufgaben zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b4c43-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="b4c43-112">Da eine übergeordnete Aufgabe nicht beendet wird, ehe alle untergeordneten Aufgaben abgeschlossen sind, kann eine untergeordnete Aufgabe mit langer Laufzeit zu einer Verschlechterung der Leistung der gesamten Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="b4c43-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="b4c43-113">Wenn die Anwendung in diesem Beispiel die Standardoptionen verwendet, um die übergeordnete Aufgabe zu erstellen, muss die untergeordnete Aufgabe vor der übergeordneten Aufgabe beendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4c43-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="b4c43-114">Wenn die Anwendung die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>-Option verwendet, wird das untergeordnete Element nicht dem übergeordneten angefügt.</span><span class="sxs-lookup"><span data-stu-id="b4c43-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="b4c43-115">Aus diesem Grund kann die Anwendung zusätzliche Aufgaben ausführen, nachdem die übergeordnete Aufgabe abgeschlossen ist, und vorher muss sie auf das Beenden der untergeordneten Aufgabe warten.</span><span class="sxs-lookup"><span data-stu-id="b4c43-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4c43-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b4c43-116">Compiling the Code</span></span>  
 <span data-ttu-id="b4c43-117">Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DenyChildAttach.cs` (`DenyChildAttach.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4c43-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DenyChildAttach.cs` (`DenyChildAttach.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="b4c43-118">**csc.exe DenyChildAttach.cs**</span><span class="sxs-lookup"><span data-stu-id="b4c43-118">**csc.exe DenyChildAttach.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="b4c43-119">**vbc.exe DenyChildAttach.vb**</span><span class="sxs-lookup"><span data-stu-id="b4c43-119">**vbc.exe DenyChildAttach.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b4c43-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b4c43-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c43-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4c43-121">See Also</span></span>  
 [<span data-ttu-id="b4c43-122">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="b4c43-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
