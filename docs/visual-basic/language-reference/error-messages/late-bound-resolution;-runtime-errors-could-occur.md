---
title: "Spät gebundene Auflösung. Laufzeitfehler sind möglich | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
dev_langs:
- VB
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
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
ms.openlocfilehash: 3baf28a17077d255b42f38ade21ce6153c24e862
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="4fa37-102">Spät gebundene Auflösung. Laufzeitfehler sind möglich.</span><span class="sxs-lookup"><span data-stu-id="4fa37-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="4fa37-103">Ein Objekt einer deklarierten Variablen zugewiesen ist die [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="4fa37-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="4fa37-104">Wenn Sie eine Variable deklarieren `Object`, muss der Compiler eine *späte Bindung*, wodurch zusätzliche Operationen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="4fa37-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="4fa37-105">Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus.</span><span class="sxs-lookup"><span data-stu-id="4fa37-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="4fa37-106">Angenommen, Sie weisen eine <xref:System.Windows.Forms.Form>auf die `Object` Variable, und wiederholen Sie den Zugriff auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>-Eigenschaft, löst die Laufzeit eine <xref:System.MemberAccessException>da die <xref:System.Windows.Forms.Form>Klasse macht eine `NameTable` Eigenschaft.</xref:System.Windows.Forms.Form> </xref:System.MemberAccessException> </xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> </xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="4fa37-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="4fa37-107">Wenn Sie die Variable eines bestimmten Typs deklarieren, kann der Compiler ausführen *frühe Bindung* zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="4fa37-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="4fa37-108">Dies führt zu einer Leistungssteigerung, kontrollierten Zugriff auf die Member des angegebenen Typs und einer besseren Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="4fa37-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="4fa37-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="4fa37-109">By default, this message is a warning.</span></span> <span data-ttu-id="4fa37-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4fa37-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4fa37-111">**Fehler-ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="4fa37-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4fa37-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4fa37-112">To correct this error</span></span>  
  
-   <span data-ttu-id="4fa37-113">Wenn möglich, deklarieren Sie die Variable eines bestimmten Typs sein.</span><span class="sxs-lookup"><span data-stu-id="4fa37-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa37-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fa37-114">See Also</span></span>  
 <span data-ttu-id="4fa37-115">[Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="4fa37-115">[Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="4fa37-116"> [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)</span><span class="sxs-lookup"><span data-stu-id="4fa37-116"> [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)</span></span>
