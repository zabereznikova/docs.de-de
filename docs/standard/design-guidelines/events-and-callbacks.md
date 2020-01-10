---
title: Ereignisse und Rückrufe
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709412"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="49d5f-102">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="49d5f-102">Events and Callbacks</span></span>
<span data-ttu-id="49d5f-103">Rückrufe sind Erweiterungs Punkte, mit denen ein Framework über einen Delegaten den Benutzercode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="49d5f-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="49d5f-104">Diese Delegaten werden in der Regel über einen Parameter einer Methode an das Framework übergeben.</span><span class="sxs-lookup"><span data-stu-id="49d5f-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="49d5f-105">Ereignisse sind ein Sonderfall von Rückrufen, die eine bequeme und konsistente Syntax für die Bereitstellung des Delegaten (eines Ereignis Handlers) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="49d5f-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="49d5f-106">Außerdem bieten die Visual Studio-Anweisungs Vervollständigung und Designer Hilfe bei der Verwendung von ereignisbasierten APIs.</span><span class="sxs-lookup"><span data-stu-id="49d5f-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="49d5f-107">(Siehe [Ereignis Entwurf](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="49d5f-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="49d5f-108">**✓ CONSIDER** Verwendung von Rückrufen Benutzer geben Sie benutzerdefinierten Code, der durch das Framework ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="49d5f-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="49d5f-109">**✓ CONSIDER** Ereignisse verwenden, um Benutzern das Anpassen des Verhaltens von einem Framework ohne die Notwendigkeit, um zu verstehen, eines objektorientierten Entwurfs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="49d5f-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="49d5f-110">**✓ DO** plain Rückrufe Ereignisse vorziehen, da sie mehr zu einem breiteren Spektrum von Entwicklern vertraut sind und mit Visual Studio-Anweisungsvervollständigung integriert sind.</span><span class="sxs-lookup"><span data-stu-id="49d5f-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="49d5f-111">**X AVOID** Rückrufe in leistungsabhängigen-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="49d5f-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="49d5f-112">**✓ DO** verwenden Sie die neue `Func<...>`, `Action<...>`, oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten, wenn APIs mit Rückrufe zu definieren.</span><span class="sxs-lookup"><span data-stu-id="49d5f-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="49d5f-113">`Func<...>` und `Action<...>` stellen generische Delegaten dar.</span><span class="sxs-lookup"><span data-stu-id="49d5f-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="49d5f-114">`Expression<...>` stellt Funktionsdefinitionen dar, die kompiliert und anschließend zur Laufzeit aufgerufen werden können, aber auch serialisiert und an Remote Prozesse weitergegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="49d5f-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="49d5f-115">**✓ DO** messen und Verstehen von Auswirkungen auf die Leistung der Verwendung von `Expression<...>`, anstatt `Func<...>` und `Action<...>` Delegaten.</span><span class="sxs-lookup"><span data-stu-id="49d5f-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="49d5f-116">`Expression<...>` Typen sind in den meisten Fällen logisch äquivalent zu `Func<...>` und `Action<...>` Delegaten.</span><span class="sxs-lookup"><span data-stu-id="49d5f-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="49d5f-117">Der Hauptunterschied besteht darin, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen. Ausdrücke sind für Fälle gedacht, in denen es vorteilhaft und möglich ist, den Ausdruck in einem Remote Prozess oder-Computer auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="49d5f-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="49d5f-118">**✓ DO** verstehen, dass durch den Aufruf eines Delegaten, beliebigen Code ausführen und bei denen konnte Sicherheit, Richtigkeit und Kompatibilität Verarbeitungsverhaltens.</span><span class="sxs-lookup"><span data-stu-id="49d5f-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="49d5f-119">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="49d5f-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="49d5f-120">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="49d5f-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d5f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49d5f-121">See also</span></span>

- [<span data-ttu-id="49d5f-122">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="49d5f-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="49d5f-123">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="49d5f-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
