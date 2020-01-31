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
ms.openlocfilehash: 7dab759ba48104530fc41e46f6f2bba18d6c4456
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741656"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="09ac4-102">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="09ac4-102">Events and Callbacks</span></span>
<span data-ttu-id="09ac4-103">Rückrufe sind Erweiterungs Punkte, mit denen ein Framework über einen Delegaten den Benutzercode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="09ac4-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="09ac4-104">Diese Delegaten werden in der Regel über einen Parameter einer Methode an das Framework übergeben.</span><span class="sxs-lookup"><span data-stu-id="09ac4-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="09ac4-105">Ereignisse sind ein Sonderfall von Rückrufen, die eine bequeme und konsistente Syntax für die Bereitstellung des Delegaten (eines Ereignis Handlers) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="09ac4-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="09ac4-106">Außerdem bieten die Visual Studio-Anweisungs Vervollständigung und Designer Hilfe bei der Verwendung von ereignisbasierten APIs.</span><span class="sxs-lookup"><span data-stu-id="09ac4-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="09ac4-107">(Siehe [Ereignis Entwurf](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="09ac4-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>

 <span data-ttu-id="09ac4-108">✔️ sollten die Verwendung von Rückrufen in Erwägung gezogen werden, damit Benutzer benutzerdefinierten Code bereitstellen können, der vom Framework ausgeführt werden kann</span><span class="sxs-lookup"><span data-stu-id="09ac4-108">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="09ac4-109">✔️ sollten Sie die Verwendung von Ereignissen in Erwägung gezogen, um Benutzern das Anpassen des Verhaltens eines Frameworks zu ermöglichen, ohne den objektorientierten Entwurf verstehen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="09ac4-109">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="09ac4-110">✔️ bevorzugen Ereignisse über einfache Rückrufe, da Sie einer breiteren Palette von Entwicklern vertraut sind und in die Visual Studio-Anweisungs Vervollständigung integriert sind.</span><span class="sxs-lookup"><span data-stu-id="09ac4-110">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="09ac4-111">❌ sollten keine Rückrufe in Leistungs sensiblen APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="09ac4-111">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="09ac4-112">beim Definieren von APIs mit Rückrufen ✔️ die neuen `Func<...>`, `Action<...>`oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="09ac4-112">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="09ac4-113">`Func<...>` und `Action<...>` stellen generische Delegaten dar.</span><span class="sxs-lookup"><span data-stu-id="09ac4-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="09ac4-114">`Expression<...>` stellt Funktionsdefinitionen dar, die kompiliert und anschließend zur Laufzeit aufgerufen werden können, aber auch serialisiert und an Remote Prozesse weitergegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="09ac4-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="09ac4-115">✔️ können die Leistungseinbußen bei der Verwendung von `Expression<...>`Messen und verstehen, anstatt `Func<...>` und `Action<...>` Delegaten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="09ac4-115">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="09ac4-116">`Expression<...>` Typen sind in den meisten Fällen logisch äquivalent zu `Func<...>` und `Action<...>` Delegaten.</span><span class="sxs-lookup"><span data-stu-id="09ac4-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="09ac4-117">Der Hauptunterschied besteht darin, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen. Ausdrücke sind für Fälle gedacht, in denen es vorteilhaft und möglich ist, den Ausdruck in einem Remote Prozess oder-Computer auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="09ac4-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="09ac4-118">✔️ verstehen, dass Sie durch Aufrufen eines Delegaten beliebigen Code ausführen, der Sicherheits-, Richtigkeit-und Kompatibilitäts Auswirkungen haben kann.</span><span class="sxs-lookup"><span data-stu-id="09ac4-118">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="09ac4-119">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="09ac4-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="09ac4-120">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="09ac4-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="09ac4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09ac4-121">See also</span></span>

- [<span data-ttu-id="09ac4-122">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="09ac4-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="09ac4-123">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="09ac4-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
