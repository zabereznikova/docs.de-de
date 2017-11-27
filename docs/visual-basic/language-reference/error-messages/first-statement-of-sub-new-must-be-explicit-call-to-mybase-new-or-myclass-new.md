---
title: 'Die erste Anweisung dieser &#39; Sub New &#39; ein expliziter Aufruf von &#39;muss sein. MyBase.New &#39; oder &#39; MyClass.New &#39; Da die &#39; &lt;Konstruktorname&gt;&#39; in der Basisklasse &#39;&lt; Basisklassenname&gt;&#39; &#39;&lt; Name der abgeleiteten Klasse&gt;&#39; ist als veraltet markiert: &#39;&lt; ErrorMessage&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords: BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="6e07c-102">Die erste Anweisung dieser &#39; Sub New &#39; ein expliziter Aufruf von &#39;muss sein. MyBase.New &#39; oder &#39; MyClass.New &#39; Da die &#39; &lt;Konstruktorname&gt;&#39; in der Basisklasse &#39;&lt; Basisklassenname&gt;&#39; &#39;&lt; Name der abgeleiteten Klasse&gt;&#39; ist als veraltet markiert: &#39;&lt; ErrorMessage&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="6e07c-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="6e07c-103">Ein Klassenkonstruktor ruft nicht explizit einen Basisklassenkonstruktor auf, und der implizite Basisklassenkonstruktor ist mit dem Attribut <xref:System.ObsoleteAttribute> und der Direktive versehen, dies als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="6e07c-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="6e07c-104">Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft, versucht [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] , einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6e07c-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="6e07c-105">Wenn kein zugänglicher Konstruktor in der Basisklasse vorhanden ist, der ohne Argumente aufgerufen werden kann, kann [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keinen impliziten Aufruf generieren.</span><span class="sxs-lookup"><span data-stu-id="6e07c-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="6e07c-106">In diesem Fall wird der erforderliche Konstruktor mit dem <xref:System.ObsoleteAttribute> -Attribut markiert, damit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ihn nicht aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="6e07c-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="6e07c-107">Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden.</span><span class="sxs-lookup"><span data-stu-id="6e07c-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="6e07c-108">Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen.</span><span class="sxs-lookup"><span data-stu-id="6e07c-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="6e07c-109">Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler.</span><span class="sxs-lookup"><span data-stu-id="6e07c-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="6e07c-110">Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="6e07c-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="6e07c-111">**Fehler-ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="6e07c-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6e07c-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6e07c-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="6e07c-113">Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="6e07c-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="6e07c-114">Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="6e07c-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e07c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e07c-115">See Also</span></span>  
 [<span data-ttu-id="6e07c-116">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="6e07c-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
