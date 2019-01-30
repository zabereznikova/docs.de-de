---
title: 'Die erste Anweisung des Sub New-Blocks muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da "<constructorname>" in der <baseclassname>-Basisklasse von "<derivedclassname>" als veraltet markiert ist: "<errormessage>"'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 31f92d1e52e50b2a87fd6a6af6e3c87292f4437f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268794"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="2093c-102">Die erste Anweisung dieser "Sub New" muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da die '\<Konstruktorname >' in der Basisklasse\<Basisklassenname >' von '\<Name der abgeleiteten Klasse > "als veraltet markiert ist:"\< Fehlermeldung >'</span><span class="sxs-lookup"><span data-stu-id="2093c-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>
<span data-ttu-id="2093c-103">Ein Klassenkonstruktor ruft nicht explizit einen Basisklassenkonstruktor auf, und der implizite Basisklassenkonstruktor ist mit dem Attribut <xref:System.ObsoleteAttribute> und der Direktive versehen, dies als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="2093c-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="2093c-104">Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft, versucht Visual Basic einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2093c-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="2093c-105">Ist es kein zugänglicher Konstruktor in der Basisklasse, die ohne Argumente aufgerufen werden kann, kann nicht in Visual Basic einen impliziten Aufruf generieren.</span><span class="sxs-lookup"><span data-stu-id="2093c-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="2093c-106">In diesem Fall wird der erforderliche Konstruktor mit markiert die <xref:System.ObsoleteAttribute> Attribut, sodass Visual Basic nicht aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="2093c-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="2093c-107">Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden.</span><span class="sxs-lookup"><span data-stu-id="2093c-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="2093c-108">Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen.</span><span class="sxs-lookup"><span data-stu-id="2093c-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="2093c-109">Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler.</span><span class="sxs-lookup"><span data-stu-id="2093c-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="2093c-110">Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="2093c-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="2093c-111">**Fehler-ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="2093c-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2093c-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2093c-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="2093c-113">Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="2093c-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="2093c-114">Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="2093c-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2093c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2093c-115">See also</span></span>
- [<span data-ttu-id="2093c-116">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="2093c-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

