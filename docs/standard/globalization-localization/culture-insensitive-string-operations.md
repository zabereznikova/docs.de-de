---
title: "Kulturunabhängige Zeichenfolgenoperationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dddd46dc5d825738dd9d5038ae573910122953c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="culture-insensitive-string-operations"></a><span data-ttu-id="f95d3-102">Kulturunabhängige Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="f95d3-102">Culture-Insensitive String Operations</span></span>
<span data-ttu-id="f95d3-103">Kulturabhängige Zeichenfolgenoperationen können von Vorteil sein, wenn Sie Anwendungen erstellen, mit denen Benutzern Ergebnisse auf Kulturbasis angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f95d3-103">Culture-sensitive string operations can be an advantage if you are creating applications designed to display results to users on a per-culture basis.</span></span> <span data-ttu-id="f95d3-104">In der Standardeinstellung rufen kulturabhängige Methoden die zu verwendende Kultur aus der <xref:System.Globalization.CultureInfo.CurrentCulture%2A>-Eigenschaft für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="f95d3-104">By default, culture-sensitive methods obtain the culture to use from the <xref:System.Globalization.CultureInfo.CurrentCulture%2A> property for the current thread.</span></span>  
  
 <span data-ttu-id="f95d3-105">Kulturabhängige Zeichenfolgenoperationen stellen jedoch nicht immer das gewünschte Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="f95d3-105">Note that culture-sensitive string operations are not always the desired behavior.</span></span> <span data-ttu-id="f95d3-106">Die Verwendung von kulturabhängigen Operationen in Szenarien, in denen die Ergebnisse unabhängig von der Kultur sein sollen, kann bei Kulturen mit speziellen Groß- und Kleinschreibungs- und Sortierungsregeln zum Fehlschlagen des Anwendungscodes führen.</span><span class="sxs-lookup"><span data-stu-id="f95d3-106">Using culture-sensitive operations when results should be independent of culture can cause application code to fail on cultures with custom case mappings and sorting rules.</span></span> <span data-ttu-id="f95d3-107">Ein Beispiel finden Sie im Abschnitt "Zeichenfolge vergleichen, verwenden die aktuelle Kultur" in der [bewährte Methoden für die Verwendung von Zeichenfolgen](../../../docs/standard/base-types/best-practices-strings.md) Artikel.</span><span class="sxs-lookup"><span data-stu-id="f95d3-107">For an example, see the "String Comparisons that Use the Current Culture" section in the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article.</span></span>  
  
 <span data-ttu-id="f95d3-108">Die zu verwendenden Zeichenfolgenoperationen (kulturabhängig oder -unabhängig) richten sich danach, wie die Ergebnisse von der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f95d3-108">Whether string operations should be culture-sensitive or culture-insensitive depends on how your application uses the results.</span></span> <span data-ttu-id="f95d3-109">Zeichenfolgenoperationen, die dem Benutzer Ergebnisse anzeigen, sollten i. d. R. kulturabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="f95d3-109">String operations that display results to the user should typically be culture-sensitive.</span></span> <span data-ttu-id="f95d3-110">Wenn eine Anwendung in einem Listenfeld z. B. eine sortierte Liste lokalisierter Zeichenfolgen anzeigt, sollte die Anwendung eine kulturabhängige Sortierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="f95d3-110">For example, if an application displays a sorted list of localized strings in a list box, the application should perform a culture-sensitive sort.</span></span>  
  
 <span data-ttu-id="f95d3-111">Ergebnisse von intern verwendeten Zeichenfolgenoperationen, sollten i. d. R. kulturunabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="f95d3-111">Results of string operations that are used internally should typically be culture-insensitive.</span></span> <span data-ttu-id="f95d3-112">Ergebnisse von Zeichenfolgenoperationen sollten sich im Allgemeinen nicht von Kultur zu Kultur unterscheiden, wenn die Anwendung Dateinamen, Persistenzformate oder Symbolinformationen verwendet, die dem Benutzer nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f95d3-112">In general, if the application is working with file names, persistence formats, or symbolic information that is not displayed to the user, results of string operations should not vary by culture.</span></span> <span data-ttu-id="f95d3-113">Wenn eine Anwendung z. B. einen Vergleich durchführt, um festzustellen, ob es sich um ein anerkanntes XML-Tag handelt, sollte der Vergleich kulturunabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="f95d3-113">For example, if an application compares a string to determine whether it is a recognized XML tag, the comparison should not be culture-sensitive.</span></span> <span data-ttu-id="f95d3-114">Wenn darüber hinaus eine Sicherheitsentscheidung auf dem Ergebnis eines Zeichenfolgenvergleichs oder einer Änderung der Groß-/Kleinschreibung beruht, sollte die Operation kulturunabhängig sein, um sicherzustellen, dass das Ergebnis nicht durch den Wert von <xref:System.Globalization.CultureInfo.CurrentCulture%2A> beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="f95d3-114">In addition, if a security decision is based on the result of a string comparison or case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span></span>  
  
 <span data-ttu-id="f95d3-115">Unabhängig davon, ob die von Ihnen entwickelte Anwendung Code zur Behandlung von Lokalisierungs- und Globalisierungsproblemen enthält, müssen Sie die .NET Framework-Methoden kennen, die in der Standardeinstellung kulturabhängige Ergebnisse abrufen.</span><span class="sxs-lookup"><span data-stu-id="f95d3-115">Whether or not you are developing an application that includes code to handle localization and globalization issues, you should be aware of the .NET Framework methods that retrieve culture-sensitive results by default.</span></span> <span data-ttu-id="f95d3-116">Aus diesem Grund wird in diesem Thema erläutert, wie die Anwendungen diese Methoden ordnungsgemäß verwenden, um kulturunabhängige Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f95d3-116">The purpose of this topic is to illustrate the correct way for your applications to use these methods to obtain culture-insensitive results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f95d3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f95d3-117">See Also</span></span>  
 [<span data-ttu-id="f95d3-118">Globalisierung und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="f95d3-118">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
