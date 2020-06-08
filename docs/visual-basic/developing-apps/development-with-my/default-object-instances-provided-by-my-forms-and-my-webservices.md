---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 847724450ee2bc8bc591371f71171e8ba4ed9337
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411739"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="03392-102">Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03392-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="03392-103">Die Objekte [My.Forms](../../language-reference/objects/my-forms-object.md) und [My.WebServices](../../language-reference/objects/my-webservices-object.md), ermöglichen den Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03392-103">The [My.Forms](../../language-reference/objects/my-forms-object.md) and [My.WebServices](../../language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="03392-104">Hierfür werden Sammlungen mit den *Standardinstanzen* jedes dieser Objekte bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="03392-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="03392-105">Standardinstanzen</span><span class="sxs-lookup"><span data-stu-id="03392-105">Default Instances</span></span>  

 <span data-ttu-id="03392-106">Eine Standardinstanz ist eine Instanz der Klasse, die von der Runtime bereitgestellt wird und nicht mit den Anweisungen `Dim` und `New` deklariert und instanziiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="03392-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="03392-107">Im folgenden Beispiel wird veranschaulicht, wie Sie mit einer deklarierten und instanziierten Instanz einer <xref:System.Windows.Forms.Form>-Klasse namens `Form1` eine Standardinstanz dieser <xref:System.Windows.Forms.Form>-Klasse über `My.Forms` erstellen können.</span><span class="sxs-lookup"><span data-stu-id="03392-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="03392-108">Das `My.Forms`-Objekt gibt eine Sammlung der Standardinstanzen für jede `Form`-Klasse zurück, die in Ihrem Projekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="03392-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="03392-109">Ebenso stellt `My.WebServices` eine Standardinstanz der Proxyklasse für jeden Webdienst bereit, auf den Sie in der Anwendung einen Verweis erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="03392-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03392-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03392-110">See also</span></span>

- [<span data-ttu-id="03392-111">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="03392-111">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="03392-112">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="03392-112">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="03392-113">Merkmale von "My" auf Grundlage des Projekttyps</span><span class="sxs-lookup"><span data-stu-id="03392-113">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
