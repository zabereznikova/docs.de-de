---
title: '&quot;&lt;Elementname&gt;&quot;ist veraltet (Visual Basic-Warnung) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
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
ms.openlocfilehash: 77708f052f7aec7a5da2b24605ba3bd794f83979
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="8815e-102">'&lt;Elementname&gt;"ist veraltet (Visual Basic-Warnung)</span><span class="sxs-lookup"><span data-stu-id="8815e-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="8815e-103">Eine Anweisung versucht, auf ein Programmierelement zuzugreifen, das mit markiert wurde das <xref:System.ObsoleteAttribute>-Attribut und der Direktive, dies als Warnung zu behandeln.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="8815e-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="8815e-104">Sie können eines beliebigen Programmierelements als nicht mehr in Gebrauch durch <xref:System.ObsoleteAttribute>darauf</xref:System.ObsoleteAttribute> anwenden markieren.</span><span class="sxs-lookup"><span data-stu-id="8815e-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="8815e-105">Wenn Sie dies tun, können Sie festlegen, dass des Attributs <xref:System.ObsoleteAttribute.IsError%2A>-Eigenschaft entweder `True` oder `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="8815e-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="8815e-106">Wenn Sie sie auf `True`festlegen, behandelt der Compiler den Versuch, das Element zu verwenden, als Fehler.</span><span class="sxs-lookup"><span data-stu-id="8815e-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="8815e-107">Wenn Sie sie auf `False`festlegen oder die Standardeinstellung `False`übernehmen, gibt der Compiler bei dem Versuch, das Element zu verwenden, eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="8815e-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="8815e-108">Standardmäßig ist diese Meldung eine Warnung, da die <xref:System.ObsoleteAttribute.IsError%2A>-Eigenschaft des <xref:System.ObsoleteAttribute>ist `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="8815e-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="8815e-109">Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8815e-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8815e-110">**Fehler-ID:** BC40008</span><span class="sxs-lookup"><span data-stu-id="8815e-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8815e-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8815e-111">To correct this error</span></span>  
  
-   <span data-ttu-id="8815e-112">Stellen Sie sicher, dass der Elementname im Quellcodeverweis richtig geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="8815e-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8815e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8815e-113">See Also</span></span>  
 [<span data-ttu-id="8815e-114">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="8815e-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

