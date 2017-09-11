---
title: 'Gewusst wie: Verwenden des My-Namespaces (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56577ff61c3f637c8e5a0969ae75d65d24ddaef7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="36f73-102">Gewusst wie: Verwenden des My-Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="36f73-102">How to: Use the My Namespace (C# Programming Guide)</span></span>
<span data-ttu-id="36f73-103">Der <xref:Microsoft.VisualBasic.MyServices>-Namespace (`My` in Visual Basic) bietet einfachen und intuitiven Zugriff auf mehrere .NET Framework-Klassen, mit denen Sie Code schreiben können, der mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagiert.</span><span class="sxs-lookup"><span data-stu-id="36f73-103">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET Framework classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="36f73-104">Auch wenn er ursprünglich für Visual Basic entwickelt wurde, kann der `MyServices`-Namespace auch in C#-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36f73-104">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="36f73-105">Weitere Informationen zum Verwenden des `MyServices`-Namespace in Visual Basic finden Sie unter [Development with My (Entwicklung mit „My“)](../../../visual-basic/developing-apps/development-with-my/index.md).</span><span class="sxs-lookup"><span data-stu-id="36f73-105">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="adding-a-reference"></a><span data-ttu-id="36f73-106">Hinzufügen eines Verweises</span><span class="sxs-lookup"><span data-stu-id="36f73-106">Adding a Reference</span></span>  
 <span data-ttu-id="36f73-107">Bevor Sie die `MyServices`-Klassen in Ihrer Projektmappe verwenden, müssen Sie einen Verweis auf die Visual Basic-Bibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36f73-107">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="36f73-108">So fügen Sie einen Verweis auf die Visual Basic-Bibliothek hinzu</span><span class="sxs-lookup"><span data-stu-id="36f73-108">To add a reference to the Visual Basic library</span></span>  
  
1.  <span data-ttu-id="36f73-109">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="36f73-109">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="36f73-110">Wenn das Dialogfeld **Verweise** geöffnet wird, durchscrollen Sie die Liste, und klicken Sie auf „Microsoft.VisualBasic.dll“.</span><span class="sxs-lookup"><span data-stu-id="36f73-110">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="36f73-111">Sie sollten auch die folgende Zeile im Abschnitt `using` am Anfang Ihres Programms einfügen.</span><span class="sxs-lookup"><span data-stu-id="36f73-111">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     <span data-ttu-id="36f73-112">[!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="36f73-112">[!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="36f73-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36f73-113">Example</span></span>  
 <span data-ttu-id="36f73-114">In diesem Beispiel werden mehrere statische Methoden aufgerufen, die im `MyServices`-Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="36f73-114">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="36f73-115">Damit dieser Code kompiliert wird, muss dem Projekt ein Verweis auf „Microsoft.VisualBasic.dll“ hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="36f73-115">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 <span data-ttu-id="36f73-116">[!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="36f73-116">[!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]</span></span>  
  
 <span data-ttu-id="36f73-117">Nicht alle Klassen des `MyServices`-Namespace können aus einer C#-Anwendung aufgerufen werden: die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>-Klasse ist z.B. nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="36f73-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="36f73-118">In diesem Fall können stattdessen die statischen Methoden verwendet werden, die Teil von <xref:Microsoft.VisualBasic.FileIO.FileSystem> sind und die außerdem in „VisualBasic.dll“ enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="36f73-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="36f73-119">So können Sie z.B. eine derartige Methode verwenden, um ein Verzeichnis zu duplizieren:</span><span class="sxs-lookup"><span data-stu-id="36f73-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 <span data-ttu-id="36f73-120">[!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="36f73-120">[!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f73-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36f73-121">See Also</span></span>  
 <span data-ttu-id="36f73-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="36f73-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="36f73-123">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="36f73-123">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 [<span data-ttu-id="36f73-124">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="36f73-124">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)

