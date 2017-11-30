---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44265c3f6f38a001192a8d92f2fbb6edeaca21cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="e682f-102">Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e682f-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="e682f-103">Die [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) und [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) -Objekte ermöglichen den Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von Ihrer Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e682f-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="e682f-104">Dies geschieht durch die Bereitstellung von Auflistungen von *Standardinstanzen* jedes dieser Objekte.</span><span class="sxs-lookup"><span data-stu-id="e682f-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="e682f-105">Standard-Instanzen</span><span class="sxs-lookup"><span data-stu-id="e682f-105">Default Instances</span></span>  
 <span data-ttu-id="e682f-106">Eine Standardinstanz ist eine Instanz der Klasse, die von der Laufzeit bereitgestellt und muss nicht werden deklariert und instanziiert wird, mithilfe der `Dim` und `New` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e682f-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="e682f-107">Im folgende Beispiel wird veranschaulicht, wie Sie möglicherweise haben deklariert und instanziiert eine Instanz von einem <xref:System.Windows.Forms.Form> Klasse mit dem Namen `Form1`, und wie Sie jetzt eine Standardinstanz dieser abrufen können <xref:System.Windows.Forms.Form> -Klasse über `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="e682f-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 <span data-ttu-id="e682f-108">Die `My.Forms` Objekt zurückgibt, eine Auflistung von Standardinstanzen für jede `Form` -Klasse, die in Ihrem Projekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e682f-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="e682f-109">Auf ähnliche Weise `My.WebServices` bietet Sie einer Standardinstanz der Proxyklasse für jeden Webdienst, dass Sie einen Verweis auf in der Anwendung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e682f-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e682f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e682f-110">See Also</span></span>  
 [<span data-ttu-id="e682f-111">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="e682f-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="e682f-112">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="e682f-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="e682f-113">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="e682f-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
