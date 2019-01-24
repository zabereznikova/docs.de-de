---
title: Spät gebundene Auflösung. Laufzeitfehler sind möglich.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 9caf02907e4b6de4c2bd8de778d4ad7a9320a82b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690578"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="06f33-102">Spät gebundene Auflösung. Laufzeitfehler sind möglich.</span><span class="sxs-lookup"><span data-stu-id="06f33-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="06f33-103">Ein Objekt erhält, eine Variable deklariert die [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="06f33-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="06f33-104">Wenn Sie eine Variable deklarieren `Object`, muss der Compiler eine *späte Bindung*, die zur Laufzeit zusätzliche Vorgänge verursacht.</span><span class="sxs-lookup"><span data-stu-id="06f33-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="06f33-105">Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus.</span><span class="sxs-lookup"><span data-stu-id="06f33-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="06f33-106">Angenommen, Sie weisen eine <xref:System.Windows.Forms.Form> zu der `Object` Variable, und wiederholen Sie dann auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> -Eigenschaft, löst die Laufzeit eine <xref:System.MemberAccessException> da die <xref:System.Windows.Forms.Form> -Klasse macht keinen verfügbar eine `NameTable` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="06f33-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="06f33-107">Wenn Sie die Variable einen bestimmten Typ deklarieren, kann der Compiler führen *frühe Bindung* zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="06f33-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="06f33-108">Dies führt zu einer Verbesserung der Leistung kontrollierten Zugriff auf die Elemente des angegebenen Typs und einer besseren Lesbarkeit Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="06f33-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="06f33-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="06f33-109">By default, this message is a warning.</span></span> <span data-ttu-id="06f33-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="06f33-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="06f33-111">**Fehler-ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="06f33-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06f33-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="06f33-112">To correct this error</span></span>  
  
-   <span data-ttu-id="06f33-113">Wenn möglich, deklarieren Sie die Variable eines bestimmten Typs sein.</span><span class="sxs-lookup"><span data-stu-id="06f33-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06f33-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06f33-114">See also</span></span>
- [<span data-ttu-id="06f33-115">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="06f33-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="06f33-116">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="06f33-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
