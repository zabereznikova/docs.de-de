---
title: Entwurf statischer Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: KrzysztofCwalina
ms.openlocfilehash: a521842d8c4651984d8d6667b93b0f28a1eba894
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130762"
---
# <a name="static-class-design"></a><span data-ttu-id="5f3aa-102">Entwurf statischer Klassen</span><span class="sxs-lookup"><span data-stu-id="5f3aa-102">Static Class Design</span></span>
<span data-ttu-id="5f3aa-103">Eine statische Klasse als eine Klasse, nur statische Member enthält, definiert ist (natürlich als Instanzmember vererbt <xref:System.Object?displayProperty=nameWithType> und möglicherweise einen privaten Konstruktor).</span><span class="sxs-lookup"><span data-stu-id="5f3aa-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="5f3aa-104">Einige Sprachen bieten integrierte Unterstützung für statische Klassen.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="5f3aa-105">In c# 2.0 und höher, wenn eine Klasse statisch deklariert wird, es ist versiegelt, "abstract", und keine Instanzmember deklariert oder außer Kraft gesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="5f3aa-106">Statische Klassen sind ein Kompromiss zwischen rein objektorientiertes Design und Einfachheit.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="5f3aa-107">Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen (z. B. <xref:System.IO.File?displayProperty=nameWithType>), werden Erweiterungsmethoden oder Funktionen, die für die ein vollständig objektorientierten Wrapper ungerechtfertigten ist (z. B. <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="5f3aa-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="5f3aa-108">**✓ DO** statische Klassen nur selten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="5f3aa-109">Statische Klassen sollten nur als Klassen zur Unterstützung für objektorientierte Core Framework verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="5f3aa-110">**X DO NOT** statische Klassen als Bucket für verschiedene Elemente behandeln.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="5f3aa-111">**X DO NOT** deklarieren oder Instanzmember in statischen Klassen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="5f3aa-112">**✓ DO** deklarieren Sie statische Klassen als versiegelt, "abstract", und fügen Sie eine private Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierten Unterstützung für statische Klassen.</span><span class="sxs-lookup"><span data-stu-id="5f3aa-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="5f3aa-113">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="5f3aa-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5f3aa-114">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="5f3aa-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3aa-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f3aa-115">See also</span></span>

- [<span data-ttu-id="5f3aa-116">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="5f3aa-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="5f3aa-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5f3aa-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
