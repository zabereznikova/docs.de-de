---
title: Die erste Anweisung dieses &quot;Sub New&quot; muss ein expliziter Aufruf an &quot;MyBase.New&quot; oder &quot;MyClass.New&quot; sein, da die &quot;&lt;Constructorname&gt;&quot;in der Basisklasse&quot;&lt;Baseclassname&gt;&quot;of&quot;&lt;Derivedclassname&gt;&quot;als veraltet markiert ist:&quot;&lt;Errormessage&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
dev_langs:
- VB
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d46192bc9a9f2807f56cbdd7bdd4fd21f6c9a7b0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="0ecfb-102">Die erste Anweisung dieses "Sub New" muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da die '&lt;Constructorname&gt;"in der Basisklasse"&lt;Baseclassname&gt;"of"&lt;Derivedclassname&gt;"als veraltet markiert ist:"&lt;Errormessage&gt;'</span><span class="sxs-lookup"><span data-stu-id="0ecfb-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="0ecfb-103">Ein Klassenkonstruktor ist nicht explizit einen Basisklassenkonstruktor aufrufen und die implizite Basisklassenkonstruktor gekennzeichnet, mit dem <xref:System.ObsoleteAttribute>-Attribut und der Direktive, dies als Fehler zu behandeln.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="0ecfb-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="0ecfb-104">Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] versucht, einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="0ecfb-105">Wenn kein zugreifbarer Konstruktor vorhanden ist, in der Basisklasse, die ohne Argumente aufgerufen werden kann [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen impliziten Aufruf kann nicht generiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="0ecfb-106">In diesem Fall wird der erforderliche Konstruktor mit markiert die <xref:System.ObsoleteAttribute>Attribut, also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] it. nicht aufrufen</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="0ecfb-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="0ecfb-107">Sie können eines beliebigen Programmierelements als nicht mehr in Gebrauch durch <xref:System.ObsoleteAttribute>darauf</xref:System.ObsoleteAttribute> anwenden markieren.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="0ecfb-108">Wenn Sie dies tun, können Sie festlegen, dass des Attributs <xref:System.ObsoleteAttribute.IsError%2A>-Eigenschaft entweder `True` oder `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="0ecfb-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="0ecfb-109">Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="0ecfb-110">Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="0ecfb-111">**Fehler-ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="0ecfb-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ecfb-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0ecfb-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="0ecfb-113">Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="0ecfb-114">Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="0ecfb-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecfb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ecfb-115">See Also</span></span>  
 [<span data-ttu-id="0ecfb-116">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="0ecfb-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
