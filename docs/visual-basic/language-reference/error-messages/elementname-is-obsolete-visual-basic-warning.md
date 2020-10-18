---
title: <elementname> ist veraltet (Visual Basic-Warnung)
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 555030d97434852eab64cc8b4bda2e901649d17d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163141"
---
# <a name="bc40008-elementname-is-obsolete-visual-basic-warning"></a><span data-ttu-id="db3e8-102">BC40008: " \<elementname> " ist veraltet (Visual Basic Warnung)</span><span class="sxs-lookup"><span data-stu-id="db3e8-102">BC40008: '\<elementname>' is obsolete (Visual Basic Warning)</span></span>

<span data-ttu-id="db3e8-103">Eine Anweisung versucht, auf ein Programmierelement zuzugreifen, das mit dem <xref:System.ObsoleteAttribute> -Attribut und der Direktive gekennzeichnet wurde, den Zugriffsversuch als Warnung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="db3e8-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>

 <span data-ttu-id="db3e8-104">Sie können jedes beliebige Programmierelement als nicht mehr in Gebrauch kennzeichnen, indem Sie <xref:System.ObsoleteAttribute> darauf anwenden.</span><span class="sxs-lookup"><span data-stu-id="db3e8-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="db3e8-105">Dabei können Sie die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft des Attributs entweder auf `True` oder `False`festlegen.</span><span class="sxs-lookup"><span data-stu-id="db3e8-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="db3e8-106">Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler.</span><span class="sxs-lookup"><span data-stu-id="db3e8-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="db3e8-107">Wenn Sie die Einstellung `False`vornehmen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="db3e8-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>

 <span data-ttu-id="db3e8-108">Diese Meldung ist standardmäßig eine Warnung, da die <xref:System.ObsoleteAttribute.IsError%2A> -Eigenschaft von <xref:System.ObsoleteAttribute> den Wert `False`aufweist.</span><span class="sxs-lookup"><span data-stu-id="db3e8-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="db3e8-109">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="db3e8-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="db3e8-110">**Fehler-ID:** BC40008</span><span class="sxs-lookup"><span data-stu-id="db3e8-110">**Error ID:** BC40008</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="db3e8-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="db3e8-111">To correct this error</span></span>

- <span data-ttu-id="db3e8-112">Stellen Sie sicher, dass der Elementname im Quellcodeverweis richtig geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="db3e8-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>

## <a name="see-also"></a><span data-ttu-id="db3e8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db3e8-113">See also</span></span>

- [<span data-ttu-id="db3e8-114">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="db3e8-114">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
