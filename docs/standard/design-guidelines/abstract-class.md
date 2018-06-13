---
title: Entwurf abstrakter Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28052cc6848d77acbdf8e9381146ca6fb06c15d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570547"
---
# <a name="abstract-class-design"></a><span data-ttu-id="9e8ff-102">Entwurf abstrakter Klassen</span><span class="sxs-lookup"><span data-stu-id="9e8ff-102">Abstract Class Design</span></span>
<span data-ttu-id="9e8ff-103">**X nicht** öffentliche oder geschützte interne Konstruktoren in abstrakten Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="9e8ff-104">Konstruktoren sollten öffentlich nur, wenn Benutzer zum Erstellen von Instanzen des Typs müssen sein.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="9e8ff-105">Da Sie die Instanzen eines abstrakten Datentyps erstellen können, ist ein abstrakter Typ mit einem öffentlichen Konstruktor falsch irreführend, für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="9e8ff-106">**Führen Sie ✓** einer geschützten oder internen-Konstruktor in abstrakten Klassen definieren.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="9e8ff-107">Ein geschützter Konstruktor ist eher üblich und einfach die Basisklasse, um eine eigene Initialisierungsschritte auszuführen. wenn Untertypen erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="9e8ff-108">Ein interner Konstruktor kann verwendet werden, beschränken Sie konkrete Implementierungen von der abstrakten Klasse auf die Assembly, die die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="9e8ff-109">**Führen Sie ✓** Geben Sie mindestens einen konkreten Typ, die von jeder abstrakten Klasse erbt, die Sie versenden.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="9e8ff-110">Dies So überprüfen Sie den Entwurf einer abstrakten Klasse.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="9e8ff-111">Beispielsweise <xref:System.IO.FileStream?displayProperty=nameWithType> ist eine Implementierung der <xref:System.IO.Stream?displayProperty=nameWithType> abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="9e8ff-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="9e8ff-112">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="9e8ff-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9e8ff-113">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="9e8ff-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8ff-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e8ff-114">See Also</span></span>  
 [<span data-ttu-id="9e8ff-115">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="9e8ff-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="9e8ff-116">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9e8ff-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
