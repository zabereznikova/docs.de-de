---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330203"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="dc38d-102">Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc38d-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="dc38d-103">Die Objekte [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) und [My. Webservices](../../../visual-basic/language-reference/objects/my-webservices-object.md) ermöglichen den Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von Ihrer Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc38d-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="dc38d-104">Hierzu werden Auflistungen von *Standard Instanzen* der einzelnen Objekte bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dc38d-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="dc38d-105">Standard Instanzen</span><span class="sxs-lookup"><span data-stu-id="dc38d-105">Default Instances</span></span>  

 <span data-ttu-id="dc38d-106">Eine Standard Instanz ist eine Instanz der-Klasse, die von der Laufzeit bereitgestellt wird und nicht mit den Anweisungen `Dim` und `New` deklariert und instanziiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="dc38d-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="dc38d-107">Im folgenden Beispiel wird veranschaulicht, wie Sie eine Instanz einer <xref:System.Windows.Forms.Form>-Klasse mit dem Namen `Form1`deklarieren und instanziiert haben und wie Sie jetzt eine Standard Instanz dieser <xref:System.Windows.Forms.Form> Klasse über `My.Forms`erhalten können.</span><span class="sxs-lookup"><span data-stu-id="dc38d-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="dc38d-108">Das `My.Forms`-Objekt gibt eine Auflistung von Standard Instanzen für jede `Form`-Klasse zurück, die in Ihrem Projekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="dc38d-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="dc38d-109">Ebenso stellt `My.WebServices` eine Standard Instanz der Proxy Klasse für jeden Webdienst bereit, auf den Sie in der Anwendung einen Verweis erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dc38d-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc38d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc38d-110">See also</span></span>

- [<span data-ttu-id="dc38d-111">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="dc38d-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="dc38d-112">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="dc38d-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="dc38d-113">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="dc38d-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
