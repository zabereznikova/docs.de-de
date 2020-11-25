---
title: Benennen von Parametern
description: Hier finden Sie Richtlinien für die Benennung von Parametern. Verwenden Sie beispielsweise beschreibende Parameternamen & Camel-Schreibweise, & Sie die Benennung basierend auf der Bedeutung anstelle des Typs in Erwägung gezogen.
ms.date: 10/22/2008
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 9f03eda511c2ef0c9565d270c52fd72bf54692d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698350"
---
# <a name="naming-parameters"></a><span data-ttu-id="4c9e1-104">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="4c9e1-104">Naming Parameters</span></span>

<span data-ttu-id="4c9e1-105">Neben dem offensichtlichen Grund für die Lesbarkeit ist es wichtig, den Richtlinien für Parameternamen zu folgen, da Parameter in der-Dokumentation und im-Designer angezeigt werden, wenn visuelle Entwurfs Tools IntelliSense-und Klassen Suchfunktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-105">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="4c9e1-106">✔️ Verwenden Sie "CamelCase" in Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-106">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="4c9e1-107">✔️ beschreibende Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-107">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="4c9e1-108">✔️ sollten Sie die Verwendung von Namen basierend auf der Bedeutung eines Parameters anstelle des Parameter Typs in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-108">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="4c9e1-109">Überladungs Parameter für Benennungs Operator</span><span class="sxs-lookup"><span data-stu-id="4c9e1-109">Naming Operator Overload Parameters</span></span>

 <span data-ttu-id="4c9e1-110">✔️ Verwenden Sie `left` und `right` für binäre Operator Überladungs Parameternamen, wenn es keine Bedeutung für die Parameter gibt.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-110">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="4c9e1-111">✔️ `value` für Überladungs Parameternamen von unären Operatoren verwenden, wenn es keine Bedeutung für die Parameter gibt.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-111">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="4c9e1-112">Wenn Sie einen signifikanten Wert hinzufügen, ✔️ aussagekräftige Namen für Operator Überladungs Parameter in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-112">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="4c9e1-113">❌ Verwenden Sie keine Abkürzungen oder numerischen Indizes für Parameternamen der Operator Überladung.</span><span class="sxs-lookup"><span data-stu-id="4c9e1-113">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="4c9e1-114">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="4c9e1-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4c9e1-115">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4c9e1-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4c9e1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c9e1-116">See also</span></span>

- [<span data-ttu-id="4c9e1-117">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4c9e1-117">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="4c9e1-118">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4c9e1-118">Naming Guidelines</span></span>](naming-guidelines.md)
