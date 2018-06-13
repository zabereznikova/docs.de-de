---
title: Unversiegelte Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571660"
---
# <a name="unsealed-classes"></a><span data-ttu-id="3f417-102">Unversiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="3f417-102">Unsealed Classes</span></span>
<span data-ttu-id="3f417-103">Versiegelte Klassen können nicht vererbt werden, aus, und sie verhindern, dass Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="3f417-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="3f417-104">Im Gegensatz dazu werden Klassen, die vom geerbt werden können, nicht versiegelte Klassen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3f417-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="3f417-105">**✓ GGF.** virtuelle oder geschützten Member mit nicht versiegelten Klassen ohne hinzugefügt werden, da eine hervorragende Möglichkeit zum kostengünstigen bereitstellen noch viel Erweiterbarkeit für ein Framework freuen.</span><span class="sxs-lookup"><span data-stu-id="3f417-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="3f417-106">Häufig möchten Entwickler von Dies ermöglicht das Hinzufügen von Mitgliedern Komfort, z. B. benutzerdefinierte Konstruktoren, Methoden oder Überladungen der Methode nicht versiegelte Klassen erben.</span><span class="sxs-lookup"><span data-stu-id="3f417-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="3f417-107">Beispielsweise `System.Messaging.MessageQueue` ist unversiegelt, und daher ermöglicht es Benutzern, die zum Erstellen von benutzerdefinierter Warteschlangen, die standardmäßig einen bestimmten Warteschlangenpfad oder Hinzufügen von benutzerdefinierten Methoden, die die API für bestimmte Szenarien zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="3f417-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="3f417-108">Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt, und dies ist auch der empfohlene Standardwert für die meisten Klassen in Frameworks.</span><span class="sxs-lookup"><span data-stu-id="3f417-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="3f417-109">Die Erweiterbarkeit von unversiegelte Typen Authentifizierungsprozesses ist viel von Framework Benutzern geschätzt und relativ ressourcenintensiv, aufgrund des relativ geringe Test-Kosten für unversiegelte Typen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3f417-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="3f417-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="3f417-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3f417-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="3f417-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f417-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f417-112">See Also</span></span>  
 [<span data-ttu-id="3f417-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3f417-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="3f417-114">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="3f417-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="3f417-115">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="3f417-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
