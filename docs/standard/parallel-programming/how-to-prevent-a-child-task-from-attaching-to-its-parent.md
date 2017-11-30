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
helpviewer_keywords: tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4717e3a077648d9db51fe39228209617b384bd0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="a6f63-102">Gewusst wie: Verhindern des Anfügens einer untergeordneten Aufgabe an die übergeordnete Aufgabe</span><span class="sxs-lookup"><span data-stu-id="a6f63-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="a6f63-103">Dieses Dokument veranschaulicht, wie eine untergeordnete Aufgabe nicht an die übergeordnete Aufgabe angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6f63-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="a6f63-104">Verhindern, dass eine untergeordnete Aufgabe mit seinem übergeordneten Element verbindet eignet sich, beim Aufrufen einer Komponente, die von einem Drittanbieter geschrieben und verwendet, die auch Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="a6f63-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="a6f63-105">Z. B. eine Drittanbieter-Komponente, verwendet der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> Option zum Erstellen einer <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> -Objekt kann Probleme im Code verursachen, wenn sie lang andauernde oder löst einen Ausnahmefehler aus.</span><span class="sxs-lookup"><span data-stu-id="a6f63-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6f63-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6f63-106">Example</span></span>  
 <span data-ttu-id="a6f63-107">Im folgenden Beispiel werden die Auswirkungen der Verwendung der Standardoptionen der Auswirkungen der verhindert, dass einer untergeordnete Aufgabe an das übergeordnete Element anfügt.</span><span class="sxs-lookup"><span data-stu-id="a6f63-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="a6f63-108">Das Beispiel erstellt eine <xref:System.Threading.Tasks.Task> -Objekt, das in einer Bibliothek eines Drittanbieters aufruft, die auch verwendet eine <xref:System.Threading.Tasks.Task> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a6f63-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="a6f63-109">Die Bibliothek eines Drittanbieters verwendet die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> Option zum Erstellen der <xref:System.Threading.Tasks.Task> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a6f63-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="a6f63-110">Die Anwendung verwendet die <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> Option aus, um die übergeordnete Aufgabe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6f63-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="a6f63-111">Diese Option weist die Laufzeit So entfernen Sie die <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> Spezifikation in untergeordneten Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="a6f63-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="a6f63-112">Da eine übergeordnete Aufgabe nicht beendet wird, ehe alle untergeordneten Aufgaben abgeschlossen sind, kann eine lang andauernde untergeordnete Aufgabe dazu führen, dass die gesamte Anwendung schlecht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6f63-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="a6f63-113">In diesem Beispiel wenn die Anwendung die Standardoptionen verwendet, um die übergeordnete Aufgabe zu erstellen muss die untergeordnete Aufgabe beendet, bevor die übergeordnete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a6f63-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="a6f63-114">Wenn die Anwendung mithilfe der <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> Option, das untergeordnete Element ist nicht an der übergeordneten Tabelle angefügt.</span><span class="sxs-lookup"><span data-stu-id="a6f63-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="a6f63-115">Aus diesem Grund kann die Anwendung zusätzliche Aufgaben ausführen, nachdem die übergeordnete Aufgabe abgeschlossen ist, und vor dem Beenden der untergeordneten Aufgabe warten muss.</span><span class="sxs-lookup"><span data-stu-id="a6f63-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6f63-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a6f63-116">Compiling the Code</span></span>  
 <span data-ttu-id="a6f63-117">Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DenyChildAttach.cs` (`DenyChildAttach.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="a6f63-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DenyChildAttach.cs` (`DenyChildAttach.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="a6f63-118">**csc.exe DenyChildAttach.cs**</span><span class="sxs-lookup"><span data-stu-id="a6f63-118">**csc.exe DenyChildAttach.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="a6f63-119">**vbc.exe DenyChildAttach.vb**</span><span class="sxs-lookup"><span data-stu-id="a6f63-119">**vbc.exe DenyChildAttach.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a6f63-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a6f63-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f63-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6f63-121">See Also</span></span>  
 [<span data-ttu-id="a6f63-122">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="a6f63-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
