---
title: "Geschützte Member"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c3aacd0f08641c01200f0b1791a78413a306590
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="protected-members"></a><span data-ttu-id="18878-102">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="18878-102">Protected Members</span></span>
<span data-ttu-id="18878-103">Geschützte Member selbst bieten keine Erweiterungen können, sie jedoch Erweiterbarkeit durch Unterklassen leistungsfähiger.</span><span class="sxs-lookup"><span data-stu-id="18878-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="18878-104">Sie können erweiterte Anpassungsoptionen verfügbar machen, ohne unnötig erschwert die wichtigsten öffentliche Schnittstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18878-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="18878-105">Framework-Entwickler müssen mit geschützte Member vorsichtig sein, da der Namen "geschützt" auf "false" wie Sicherheit geben kann.</span><span class="sxs-lookup"><span data-stu-id="18878-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="18878-106">Jeder Benutzer kann auf Unterklasse in einer unversiegelten Klasse und den Zugriff auf geschützte Member und also alle den gleichen defensive Codierungstechniken für öffentliche Member verwendet, die auf geschützte Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="18878-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="18878-107">**✓ GGF.** mit geschützte Member für die erweiterte Anpassung.</span><span class="sxs-lookup"><span data-stu-id="18878-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="18878-108">**Führen Sie ✓** geschützte Member in nicht versiegelten Klassen als öffentlich für die Sicherheit, Dokumentation und Kompatibilität Analyse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="18878-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="18878-109">Jeder kann von einer Klasse erben und die geschützten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="18878-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="18878-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="18878-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="18878-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="18878-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18878-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18878-112">See Also</span></span>  
 [<span data-ttu-id="18878-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="18878-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="18878-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="18878-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
