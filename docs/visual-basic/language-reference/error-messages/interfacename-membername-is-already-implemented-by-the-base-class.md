---
title: "'<interfacename>. <membername>'wird bereits implementiert durch die Basisklasse'<baseclassname>'. Die erneute Implementierung von <type> davon ausgegangen, dass"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 64bd7771820c2a4073350b7a5189d3a32c4775be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921328"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="572d3-103">'\<Schnittstellenname >. \<Membername >' ist bereits in der Basisklasse implementiert\<Basisklassenname >'.</span><span class="sxs-lookup"><span data-stu-id="572d3-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="572d3-104">Die erneute Implementierung von \<Typ > davon ausgegangen, dass</span><span class="sxs-lookup"><span data-stu-id="572d3-104">Re-implementation of \<type> assumed</span></span>
<span data-ttu-id="572d3-105">Eine Eigenschaft, Prozedur oder das Ereignis in einer abgeleiteten Klasse verwendet eine `Implements` -Klausel für einen Schnittstellenmember, die bereits in der Basisklasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="572d3-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="572d3-106">Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="572d3-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="572d3-107">Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="572d3-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="572d3-108">Weitere Informationen finden Sie unter [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="572d3-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="572d3-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="572d3-109">By default, this message is a warning.</span></span> <span data-ttu-id="572d3-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="572d3-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="572d3-111">**Fehler-ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="572d3-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="572d3-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="572d3-112">To correct this error</span></span>  
  
- <span data-ttu-id="572d3-113">Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen.</span><span class="sxs-lookup"><span data-stu-id="572d3-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="572d3-114">Code in der abgeleiteten Klasse greift auf die neu Member aus, es sei denn, Sie verwenden die `MyBase` Schlüsselwort, um die Implementierung der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="572d3-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
- <span data-ttu-id="572d3-115">Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="572d3-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572d3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="572d3-116">See also</span></span>

- [<span data-ttu-id="572d3-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="572d3-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
