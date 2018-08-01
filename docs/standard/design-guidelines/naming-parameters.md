---
title: Benennen von Parametern
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6b96bb05c52de4bfd8b6ad6b972c9d22ca66da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570485"
---
# <a name="naming-parameters"></a><span data-ttu-id="0ec6f-102">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="0ec6f-102">Naming Parameters</span></span>
<span data-ttu-id="0ec6f-103">Über die offensichtlichen Grund der Lesbarkeit ist es wichtig, die Richtlinien für Parameternamen zu folgen, da der Parameter in der Dokumentation und im Designer angezeigt werden, wenn visuellen Entwurfstools Intellisense und Funktionen durchsuchen Klasse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="0ec6f-104">**✓ DO** CamelCasing Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="0ec6f-105">**✓ DO** beschreibende Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="0ec6f-106">**✓ CONSIDER** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="0ec6f-107">Benennen der-Operator Überladung Parameter</span><span class="sxs-lookup"><span data-stu-id="0ec6f-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="0ec6f-108">**✓ DO** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="0ec6f-109">**✓ DO** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="0ec6f-110">**✓ CONSIDER** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="0ec6f-111">**X DO NOT** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="0ec6f-112">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0ec6f-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0ec6f-113">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="0ec6f-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec6f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ec6f-114">See Also</span></span>  
 [<span data-ttu-id="0ec6f-115">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ec6f-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0ec6f-116">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="0ec6f-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
