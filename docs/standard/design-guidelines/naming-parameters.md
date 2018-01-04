---
title: Benennen von Parametern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a10fa8835bfbcf826f8a3bb9318966e0dc603864
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="naming-parameters"></a><span data-ttu-id="e178d-102">Benennen von Parametern</span><span class="sxs-lookup"><span data-stu-id="e178d-102">Naming Parameters</span></span>
<span data-ttu-id="e178d-103">Über die offensichtlichen Grund der Lesbarkeit ist es wichtig, die Richtlinien für Parameternamen zu folgen, da der Parameter in der Dokumentation und im Designer angezeigt werden, wenn visuellen Entwurfstools Intellisense und Funktionen durchsuchen Klasse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e178d-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="e178d-104">**Führen Sie ✓** CamelCasing Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e178d-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="e178d-105">**Führen Sie ✓** beschreibende Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e178d-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="e178d-106">**✓ GGF.** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="e178d-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="e178d-107">Benennen der-Operator Überladung Parameter</span><span class="sxs-lookup"><span data-stu-id="e178d-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="e178d-108">**Führen Sie ✓** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e178d-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="e178d-109">**Führen Sie ✓** verwenden `value` für unäre Operator überladen Parameternamen, wenn keine Bedeutung für den Parameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e178d-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="e178d-110">**✓ GGF.** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also erheblichem Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e178d-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="e178d-111">**X nicht** verwenden Abkürzungen oder numerischen Indizes für Operator überladen Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="e178d-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="e178d-112">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="e178d-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e178d-113">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="e178d-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e178d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e178d-114">See Also</span></span>  
 [<span data-ttu-id="e178d-115">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e178d-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="e178d-116">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="e178d-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
