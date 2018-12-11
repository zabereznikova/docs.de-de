---
title: Geschützte Member
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: f0ad21f0a5b869332223d96991dd0a7bebeba420
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149353"
---
# <a name="protected-members"></a><span data-ttu-id="2c994-102">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="2c994-102">Protected Members</span></span>
<span data-ttu-id="2c994-103">Geschützte Member selbst bieten keine Erweiterungen, jedoch können sie Erweiterbarkeit durch Unterklassen leistungsfähiger machen.</span><span class="sxs-lookup"><span data-stu-id="2c994-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="2c994-104">Sie können verwendet werden, um erweiterte Anpassungsoptionen verfügbar zu machen, ohne unnötig verkompliziert die wichtigsten öffentliche Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2c994-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="2c994-105">Framework-Entwickler müssen mit geschützten Elementen vorsichtig sein, da ein falsches Gefühl der Sicherheit mit der Namen "geschützt" gesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2c994-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="2c994-106">Jeder Benutzer kann Unterklasse einer unversiegelten Klasse und den Zugriff auf geschützte Member, und daher die gleichen defensive Praktiken zur codeerstellung öffentliche Member zum gelten für geschützte Member.</span><span class="sxs-lookup"><span data-stu-id="2c994-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="2c994-107">**✓ CONSIDER** mit geschützte Member für die erweiterte Anpassung.</span><span class="sxs-lookup"><span data-stu-id="2c994-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="2c994-108">**✓ DO** geschützte Member in nicht versiegelten Klassen als öffentlich für die Sicherheit, Dokumentation und Kompatibilität Analyse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="2c994-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="2c994-109">Jeder kann von einer Klasse erben und die geschützten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2c994-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="2c994-110">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2c994-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2c994-111">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="2c994-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c994-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c994-112">See also</span></span>

- [<span data-ttu-id="2c994-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2c994-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="2c994-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="2c994-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
