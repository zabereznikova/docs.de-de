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
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571084"
---
# <a name="protected-members"></a><span data-ttu-id="ab3d2-102">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="ab3d2-102">Protected Members</span></span>
<span data-ttu-id="ab3d2-103">Geschützte Member selbst bieten keine Erweiterungen können, sie jedoch Erweiterbarkeit durch Unterklassen leistungsfähiger.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="ab3d2-104">Sie können erweiterte Anpassungsoptionen verfügbar machen, ohne unnötig erschwert die wichtigsten öffentliche Schnittstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="ab3d2-105">Framework-Entwickler müssen mit geschützte Member vorsichtig sein, da der Namen "geschützt" auf "false" wie Sicherheit geben kann.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="ab3d2-106">Jeder Benutzer kann auf Unterklasse in einer unversiegelten Klasse und den Zugriff auf geschützte Member und also alle den gleichen defensive Codierungstechniken für öffentliche Member verwendet, die auf geschützte Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="ab3d2-107">**✓ CONSIDER** mit geschützte Member für die erweiterte Anpassung.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="ab3d2-108">**✓ DO** geschützte Member in nicht versiegelten Klassen als öffentlich für die Sicherheit, Dokumentation und Kompatibilität Analyse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="ab3d2-109">Jeder kann von einer Klasse erben und die geschützten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ab3d2-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="ab3d2-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ab3d2-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ab3d2-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="ab3d2-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3d2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab3d2-112">See Also</span></span>  
 [<span data-ttu-id="ab3d2-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ab3d2-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="ab3d2-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ab3d2-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
