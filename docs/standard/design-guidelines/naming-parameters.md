---
title: Benennen von Parametern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 35965f03f5c50cbe3ffcc9bdb615d99c50fc30a2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147911"
---
# <a name="naming-parameters"></a><span data-ttu-id="ef3c1-102">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="ef3c1-102">Naming Parameters</span></span>
<span data-ttu-id="ef3c1-103">Nach der naheliegende Grund für lesbaren Code ist es wichtig, die Richtlinien für Parameternamen zu befolgen, da der Parameter in der Dokumentation und im Designer angezeigt werden, wenn visuellen Entwurfstools Intellisense und die Klasse, die Durchsuchen-Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="ef3c1-104">**✓ DO** CamelCasing Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="ef3c1-105">**✓ DO** beschreibende Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="ef3c1-106">**✓ CONSIDER** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="ef3c1-107">Benennen von Parametern für Operator-Überladung</span><span class="sxs-lookup"><span data-stu-id="ef3c1-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="ef3c1-108">**✓ DO** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="ef3c1-109">**✓ DO** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="ef3c1-110">**✓ CONSIDER** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="ef3c1-111">**X DO NOT** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="ef3c1-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="ef3c1-112">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ef3c1-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ef3c1-113">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="ef3c1-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3c1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef3c1-114">See also</span></span>

- [<span data-ttu-id="ef3c1-115">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ef3c1-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="ef3c1-116">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="ef3c1-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
