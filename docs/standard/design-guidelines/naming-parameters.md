---
title: Benennen von Parametern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0bb67056bb39b6a5f372191a1d0b0bb0dc1fe4d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709178"
---
# <a name="naming-parameters"></a><span data-ttu-id="12831-102">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="12831-102">Naming Parameters</span></span>
<span data-ttu-id="12831-103">Neben dem offensichtlichen Grund für die Lesbarkeit ist es wichtig, den Richtlinien für Parameternamen zu folgen, da Parameter in der-Dokumentation und im-Designer angezeigt werden, wenn visuelle Entwurfs Tools IntelliSense-und Klassen Suchfunktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="12831-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="12831-104">**✓ DO** CamelCasing Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="12831-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="12831-105">**✓ DO** beschreibende Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="12831-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="12831-106">**✓ CONSIDER** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="12831-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="12831-107">Überladungs Parameter für Benennungs Operator</span><span class="sxs-lookup"><span data-stu-id="12831-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="12831-108">**✓ DO** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="12831-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="12831-109">**✓ DO** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="12831-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="12831-110">**✓ CONSIDER** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12831-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="12831-111">**X DO NOT** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="12831-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="12831-112">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="12831-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="12831-113">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="12831-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12831-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12831-114">See also</span></span>

- [<span data-ttu-id="12831-115">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="12831-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="12831-116">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="12831-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
