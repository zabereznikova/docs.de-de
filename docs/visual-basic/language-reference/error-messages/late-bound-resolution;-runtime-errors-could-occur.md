---
title: "Spät gebundene Auflösung. Laufzeitfehler sind möglich."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords: BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="26874-102">Spät gebundene Auflösung. Laufzeitfehler sind möglich.</span><span class="sxs-lookup"><span data-stu-id="26874-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="26874-103">Eine Variable deklariert ein Objekt zugewiesen ist die [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="26874-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="26874-104">Wenn Sie eine Variable als deklarieren `Object`, muss der Compiler eine *späte Bindung*, die zur Laufzeit zusätzliche Vorgänge verursacht.</span><span class="sxs-lookup"><span data-stu-id="26874-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="26874-105">Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus.</span><span class="sxs-lookup"><span data-stu-id="26874-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="26874-106">Angenommen, Sie weisen einen <xref:System.Windows.Forms.Form> auf die `Object` Variable, und wiederholen Sie dann den Zugriff auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> -Eigenschaft, löst die Laufzeit eine <xref:System.MemberAccessException> da der <xref:System.Windows.Forms.Form> Klasse macht keine `NameTable` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="26874-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="26874-107">Wenn Sie die Variable eines bestimmten Typs deklarieren, kann der Compiler nicht ausführen *frühe Bindung* zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="26874-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="26874-108">Dies führt zu einer verbesserten Leistung, kontrollierten Zugriff auf die Elemente des angegebenen Typs und einer besseren Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="26874-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="26874-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="26874-109">By default, this message is a warning.</span></span> <span data-ttu-id="26874-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="26874-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="26874-111">**Fehler-ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="26874-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26874-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="26874-112">To correct this error</span></span>  
  
-   <span data-ttu-id="26874-113">Wenn möglich, deklarieren Sie die Variable eines bestimmten Typs sein.</span><span class="sxs-lookup"><span data-stu-id="26874-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26874-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26874-114">See Also</span></span>  
 [<span data-ttu-id="26874-115">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="26874-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="26874-116">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="26874-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
