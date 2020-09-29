---
title: 'Vorgehensweise: Verwenden des My-Namespaces (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie den My-Namespace verwenden. Der My-Namespace bietet einfachen und intuitiven Zugriff auf eine Reihe von .NET-Klassen.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 5310b911cc0abf0e82c4dc8efd45eb45ffb94c9d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176226"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="c1c4d-104">Vorgehensweise: Verwenden des My-Namespaces (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="c1c4d-104">How to use the My namespace (C# Programming Guide)</span></span>

<span data-ttu-id="c1c4d-105">Der Namespace <xref:Microsoft.VisualBasic.MyServices> (`My` in Visual Basic) bietet einen einfachen und intuitiven Zugriff auf zahlreiche .NET-Klassen. Dies ermöglicht das Erstellen von Code, der mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagiert.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-105">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="c1c4d-106">Auch wenn er ursprünglich für Visual Basic entwickelt wurde, kann der `MyServices`-Namespace auch in C#-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-106">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="c1c4d-107">Weitere Informationen zum Verwenden des `MyServices`-Namespace in Visual Basic finden Sie unter [Development with My (Entwicklung mit „My“)](../../../visual-basic/developing-apps/development-with-my/index.md).</span><span class="sxs-lookup"><span data-stu-id="c1c4d-107">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="add-a-reference"></a><span data-ttu-id="c1c4d-108">Hinzufügen eines Verweises</span><span class="sxs-lookup"><span data-stu-id="c1c4d-108">Add a reference</span></span>

 <span data-ttu-id="c1c4d-109">Bevor Sie die `MyServices`-Klassen in Ihrer Projektmappe verwenden, müssen Sie einen Verweis auf die Visual Basic-Bibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-109">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
### <a name="add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="c1c4d-110">So fügen Sie einen Verweis auf die Visual Basic-Bibliothek hinzu</span><span class="sxs-lookup"><span data-stu-id="c1c4d-110">Add a reference to the Visual Basic library</span></span>  
  
1. <span data-ttu-id="c1c4d-111">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-111">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="c1c4d-112">Wenn das Dialogfeld **Verweise** geöffnet wird, durchscrollen Sie die Liste, und klicken Sie auf „Microsoft.VisualBasic.dll“.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-112">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="c1c4d-113">Sie sollten auch die folgende Zeile im Abschnitt `using` am Anfang Ihres Programms einfügen.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-113">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a><span data-ttu-id="c1c4d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1c4d-114">Example</span></span>  

 <span data-ttu-id="c1c4d-115">In diesem Beispiel werden mehrere statische Methoden aufgerufen, die im `MyServices`-Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-115">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="c1c4d-116">Damit dieser Code kompiliert wird, muss dem Projekt ein Verweis auf „Microsoft.VisualBasic.dll“ hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-116">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 <span data-ttu-id="c1c4d-117">Nicht alle Klassen des `MyServices`-Namespace können aus einer C#-Anwendung aufgerufen werden: die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>-Klasse ist z.B. nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="c1c4d-118">In diesem Fall können stattdessen die statischen Methoden verwendet werden, die Teil von <xref:Microsoft.VisualBasic.FileIO.FileSystem> sind und die außerdem in „VisualBasic.dll“ enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c1c4d-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="c1c4d-119">So können Sie z.B. eine derartige Methode verwenden, um ein Verzeichnis zu duplizieren:</span><span class="sxs-lookup"><span data-stu-id="c1c4d-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a><span data-ttu-id="c1c4d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1c4d-120">See also</span></span>

- [<span data-ttu-id="c1c4d-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c1c4d-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c1c4d-122">Namespaces</span><span class="sxs-lookup"><span data-stu-id="c1c4d-122">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="c1c4d-123">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="c1c4d-123">Using Namespaces</span></span>](./using-namespaces.md)
