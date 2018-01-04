---
title: Entwurf statischer Klassen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8c36bf5790d033eddb6bb7e0d910482143a9bcac
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="static-class-design"></a><span data-ttu-id="8e0e3-102">Entwurf statischer Klassen</span><span class="sxs-lookup"><span data-stu-id="8e0e3-102">Static Class Design</span></span>
<span data-ttu-id="8e0e3-103">Eine statische Klasse als eine Klasse, nur statische Member enthält, definiert ist (natürlich neben der Instanzmember geerbt von <xref:System.Object?displayProperty=nameWithType> und möglicherweise einen privaten Konstruktor).</span><span class="sxs-lookup"><span data-stu-id="8e0e3-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="8e0e3-104">Für einige Sprachen bieten integrierte Unterstützung für statische Klassen.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="8e0e3-105">In c# 2.0 und höher, wenn eine Klasse als statisch deklariert ist, ist versiegelt, "abstract", und keine Instanzmember überschreiben oder deklariert werden können.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="8e0e3-106">Statische Klassen sind, einen Kompromiss zwischen reinen eines objektorientierten Entwurfs und Einfachheit.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="8e0e3-107">Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen (z. B. <xref:System.IO.File?displayProperty=nameWithType>), Inhaber von Erweiterungsmethoden [c#], oder Funktionen, die für die ein vollständige objektorientierten Wrapper unbefugten ist (z. B. <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="8e0e3-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="8e0e3-108">**Führen Sie ✓** statische Klassen nur selten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="8e0e3-109">Statische Klassen sollte nur als unterstützende Klassen für den objektorientierten Kern des Frameworks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="8e0e3-110">**X nicht** statische Klassen als Bucket für verschiedene Elemente behandeln.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="8e0e3-111">**X nicht** deklarieren oder Instanzmember in statischen Klassen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="8e0e3-112">**Führen Sie ✓** deklarieren Sie statische Klassen als versiegelt, "abstract", und fügen Sie eine private Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierten Unterstützung für statische Klassen.</span><span class="sxs-lookup"><span data-stu-id="8e0e3-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="8e0e3-113">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="8e0e3-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8e0e3-114">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="8e0e3-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e0e3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e0e3-115">See Also</span></span>  
 [<span data-ttu-id="8e0e3-116">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="8e0e3-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="8e0e3-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8e0e3-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
