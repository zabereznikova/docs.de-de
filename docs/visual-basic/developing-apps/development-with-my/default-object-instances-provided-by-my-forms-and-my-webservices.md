---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 5a81cde63de258f0996c3ddbc99e0102d58d79b8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973911"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="d184b-102">Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d184b-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="d184b-103">Die [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) und [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) Objekte bieten Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von der Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d184b-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="d184b-104">Dies erfolgt durch Bereitstellen von Sammlungen von *Standardinstanzen* jedes dieser Objekte.</span><span class="sxs-lookup"><span data-stu-id="d184b-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="d184b-105">Standard-Instanzen</span><span class="sxs-lookup"><span data-stu-id="d184b-105">Default Instances</span></span>  
 <span data-ttu-id="d184b-106">Eine Standardinstanz ist eine Instanz der Klasse, die von der Laufzeit bereitgestellt wird, und muss nicht werden deklariert und instanziiert wird, mit der `Dim` und `New` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d184b-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="d184b-107">Das folgende Beispiel zeigt, wie Sie möglicherweise haben deklariert und instanziiert eine Instanz von einer <xref:System.Windows.Forms.Form> Klasse mit dem Namen `Form1`, und wie Sie jetzt erhalten Sie eine Standardinstanz dieser <xref:System.Windows.Forms.Form> -Klasse über `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="d184b-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="d184b-108">Die `My.Forms` -Objekt gibt eine Auflistung der Standardinstanzen für jede `Form` -Klasse, die in Ihrem Projekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d184b-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="d184b-109">Auf ähnliche Weise `My.WebServices` bietet Sie einer Standardinstanz der Proxyklasse für jeden Webdienst, dass Sie einen Verweis auf in Ihrer Anwendung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d184b-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d184b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d184b-110">See also</span></span>
- [<span data-ttu-id="d184b-111">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="d184b-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="d184b-112">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="d184b-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="d184b-113">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="d184b-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
