---
title: "\"<interfacename>.<membername>\" wird bereits durch die <baseclassname>-Basisklssse implementiert. Die erneute Implementierung von <type> wird angenommen."
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 8137f6b1712b6a0752a991f5a3d598b5f958252c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162816"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="36047-103">BC42015: " \<interfacename> . \<membername> " wird bereits von der Basisklasse " \<baseclassname> " implementiert.</span><span class="sxs-lookup"><span data-stu-id="36047-103">BC42015: '\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="36047-104">Die erneute Implementierung von \<type> wird angenommen.</span><span class="sxs-lookup"><span data-stu-id="36047-104">Re-implementation of \<type> assumed</span></span>

<span data-ttu-id="36047-105">Eine Eigenschaft, Prozedur oder ein Ereignis in einer abgeleiteten Klasse verwendet eine- `Implements` Klausel, die einen Schnittstellenmember angibt, der bereits in der Basisklasse implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="36047-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>

 <span data-ttu-id="36047-106">Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="36047-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="36047-107">Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="36047-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="36047-108">Weitere Informationen finden Sie unter [Implements](../statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="36047-108">For more information, see [Implements](../statements/implements-clause.md).</span></span>

 <span data-ttu-id="36047-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="36047-109">By default, this message is a warning.</span></span> <span data-ttu-id="36047-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="36047-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="36047-111">**Fehler-ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="36047-111">**Error ID:** BC42015</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="36047-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="36047-112">To correct this error</span></span>

- <span data-ttu-id="36047-113">Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen.</span><span class="sxs-lookup"><span data-stu-id="36047-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="36047-114">Der Code in der abgeleiteten Klasse greift auf den neu implementierten Member zu, sofern Sie nicht das- `MyBase` Schlüsselwort verwenden, um auf die Basisklassen Implementierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="36047-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>

- <span data-ttu-id="36047-115">Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="36047-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="36047-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36047-116">See also</span></span>

- [<span data-ttu-id="36047-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="36047-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
