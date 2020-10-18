---
title: Spät gebundene Auflösung. Laufzeitfehler sind möglich.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: ef0fa295cadaaa0550be4809ec97c6da13b5e2db
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160430"
---
# <a name="bc42017-late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="24968-102">BC42017: spät gebundene Auflösung; Laufzeitfehler können auftreten</span><span class="sxs-lookup"><span data-stu-id="24968-102">BC42017: Late bound resolution; runtime errors could occur</span></span>

<span data-ttu-id="24968-103">Ein-Objekt wird einer Variablen zugewiesen, die als [Objekt Datentyp](../data-types/object-data-type.md)deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="24968-103">An object is assigned to a variable declared to be of the [Object Data Type](../data-types/object-data-type.md).</span></span>

 <span data-ttu-id="24968-104">Wenn Sie eine Variable als deklarieren `Object` , muss der Compiler die *späte Bindung*durchführen, die zur Laufzeit zusätzliche Vorgänge verursacht.</span><span class="sxs-lookup"><span data-stu-id="24968-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="24968-105">Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus.</span><span class="sxs-lookup"><span data-stu-id="24968-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="24968-106">Wenn Sie z. b. <xref:System.Windows.Forms.Form> der Variablen eine zuweisen `Object` und dann versuchen, auf die- <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> Eigenschaft zuzugreifen, löst die Laufzeit eine <xref:System.MemberAccessException> aus, da die- <xref:System.Windows.Forms.Form> Klasse keine-Eigenschaft verfügbar macht `NameTable` .</span><span class="sxs-lookup"><span data-stu-id="24968-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>

 <span data-ttu-id="24968-107">Wenn Sie die Variable als einen bestimmten Typ deklarieren, kann der Compiler zum Zeitpunkt der Kompilierung eine *frühe Bindung* durchführen.</span><span class="sxs-lookup"><span data-stu-id="24968-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="24968-108">Dies führt zu einer verbesserten Leistung, kontrolliertem Zugriff auf die Member des spezifischen Typs und besserer Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="24968-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>

 <span data-ttu-id="24968-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="24968-109">By default, this message is a warning.</span></span> <span data-ttu-id="24968-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="24968-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="24968-111">**Fehler-ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="24968-111">**Error ID:** BC42017</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="24968-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="24968-112">To correct this error</span></span>

- <span data-ttu-id="24968-113">Deklarieren Sie die Variable nach Möglichkeit als einen bestimmten Typ.</span><span class="sxs-lookup"><span data-stu-id="24968-113">If possible, declare the variable to be of a specific type.</span></span>

## <a name="see-also"></a><span data-ttu-id="24968-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24968-114">See also</span></span>

- [<span data-ttu-id="24968-115">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="24968-115">Early and Late Binding</span></span>](../../programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="24968-116">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="24968-116">Object Variable Declaration</span></span>](../../programming-guide/language-features/variables/object-variable-declaration.md)
