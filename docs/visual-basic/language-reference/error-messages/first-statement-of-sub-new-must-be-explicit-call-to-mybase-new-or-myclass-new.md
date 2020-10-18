---
title: 'Die erste Anweisung des Sub New-Blocks muss ein expliziter Aufruf an "MyBase.New" oder "MyClass.New" sein, da "<constructorname>" in der <baseclassname>-Basisklasse von "<derivedclassname>" als veraltet markiert ist: "<errormessage>"'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 4b927e3eed8f9d7f46255b907342465f48263724
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163037"
---
# <a name="bc30920-first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="a8fd7-102">BC30920: die erste Anweisung dieses "Sub New" muss ein expliziter Rückruf an "MyBase. New" oder "MyClass. New" sein, da "" \<constructorname> in der Basisklasse "" \<baseclassname> von " \<derivedclassname> " als veraltet markiert ist: " \<errormessage> "</span><span class="sxs-lookup"><span data-stu-id="a8fd7-102">BC30920: First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>

<span data-ttu-id="a8fd7-103">Ein Klassenkonstruktor ruft nicht explizit einen Basisklassenkonstruktor auf, und der implizite Basisklassenkonstruktor ist mit dem Attribut <xref:System.ObsoleteAttribute> und der Direktive versehen, dies als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>

 <span data-ttu-id="a8fd7-104">Wenn ein abgeleiteter Klassenkonstruktor keinen Basisklassenkonstruktor aufruft, versucht Visual Basic, einen impliziten-Befehl für einen Parameter losen Basisklassenkonstruktor zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="a8fd7-105">Wenn kein zugänglicher Konstruktor in der Basisklasse vorhanden ist, der ohne Argumente aufgerufen werden kann, kann Visual Basic keinen impliziten Aufruf generieren.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="a8fd7-106">In diesem Fall wird der erforderliche Konstruktor mit dem- <xref:System.ObsoleteAttribute> Attribut markiert, sodass Visual Basic ihn nicht abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>

 <span data-ttu-id="a8fd7-107">Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="a8fd7-108">Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="a8fd7-109">Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="a8fd7-110">Wenn Sie die Einstellung `False`vornehmen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>

 <span data-ttu-id="a8fd7-111">**Fehler-ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="a8fd7-111">**Error ID:** BC30920</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a8fd7-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a8fd7-112">To correct this error</span></span>

1. <span data-ttu-id="a8fd7-113">Überprüfen Sie die angegebene Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-113">Examine the quoted error message and take appropriate action.</span></span>

2. <span data-ttu-id="a8fd7-114">Fügen Sie einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` in der abgeleiteten Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="a8fd7-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8fd7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8fd7-115">See also</span></span>

- [<span data-ttu-id="a8fd7-116">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="a8fd7-116">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
