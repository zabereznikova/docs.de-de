---
title: Geschützte Member
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44068975"
---
# <a name="protected-members"></a><span data-ttu-id="4f906-102">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="4f906-102">Protected Members</span></span>
<span data-ttu-id="4f906-103">Geschützte Member selbst bieten keine Erweiterungen, jedoch können sie Erweiterbarkeit durch Unterklassen leistungsfähiger machen.</span><span class="sxs-lookup"><span data-stu-id="4f906-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="4f906-104">Sie können verwendet werden, um erweiterte Anpassungsoptionen verfügbar zu machen, ohne unnötig verkompliziert die wichtigsten öffentliche Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4f906-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="4f906-105">Framework-Entwickler müssen mit geschützten Elementen vorsichtig sein, da ein falsches Gefühl der Sicherheit mit der Namen "geschützt" gesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f906-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="4f906-106">Jeder Benutzer kann Unterklasse einer unversiegelten Klasse und den Zugriff auf geschützte Member, und daher die gleichen defensive Praktiken zur codeerstellung öffentliche Member zum gelten für geschützte Member.</span><span class="sxs-lookup"><span data-stu-id="4f906-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="4f906-107">**✓ CONSIDER** mit geschützte Member für die erweiterte Anpassung.</span><span class="sxs-lookup"><span data-stu-id="4f906-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="4f906-108">**✓ DO** geschützte Member in nicht versiegelten Klassen als öffentlich für die Sicherheit, Dokumentation und Kompatibilität Analyse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4f906-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="4f906-109">Jeder kann von einer Klasse erben und die geschützten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4f906-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="4f906-110">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="4f906-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4f906-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4f906-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f906-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f906-112">See also</span></span>

- [<span data-ttu-id="4f906-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4f906-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="4f906-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="4f906-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
