---
title: Feldentwurf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3249518dd1e1c751de08c22d1c5eb4fa28dc6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="field-design"></a><span data-ttu-id="78f63-102">Feldentwurf</span><span class="sxs-lookup"><span data-stu-id="78f63-102">Field Design</span></span>
<span data-ttu-id="78f63-103">Das Prinzip der Kapselung ist einer der wichtigsten Konzepte in eines objektorientierten Entwurfs.</span><span class="sxs-lookup"><span data-stu-id="78f63-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="78f63-104">Dieses Prinzip gibt an, dass in einem Objekt gespeicherte Daten nur auf dieses Objekt zugegriffen werden soll.</span><span class="sxs-lookup"><span data-stu-id="78f63-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="78f63-105">Eine gute Möglichkeit, interpretiert das Prinzip ist zu sagen, dass ein Typ, damit Änderungen an Felder des Typs (Änderungen, Name oder Typ) vorgenommen werden können, ohne Unterbrechung Code nur für Elemente des Typs entworfen werden soll.</span><span class="sxs-lookup"><span data-stu-id="78f63-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="78f63-106">Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.</span><span class="sxs-lookup"><span data-stu-id="78f63-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="78f63-107">Wir ausschließen Konstanten und statische schreibgeschützte Felder aus dieser Einschränkung strict, da Suchfelder, fast per Definition nie erforderlich sind, ändern.</span><span class="sxs-lookup"><span data-stu-id="78f63-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="78f63-108">**X nicht** bieten Instanzfelder, die öffentlich und/oder geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="78f63-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="78f63-109">Sie sollten Eigenschaften für den Zugriff auf Felder und trifft diese öffentliche oder geschützte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78f63-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="78f63-110">**Führen Sie ✓** verwenden Sie Konstante Felder für Konstanten, die nie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="78f63-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="78f63-111">Der Compiler brennt const Felder die Werte direkt in Aufrufen von Code.</span><span class="sxs-lookup"><span data-stu-id="78f63-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="78f63-112">Aus diesem Grund können Konstante Werte ohne beschädigen Kompatibilität nie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="78f63-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="78f63-113">**Führen Sie ✓** öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen.</span><span class="sxs-lookup"><span data-stu-id="78f63-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="78f63-114">Wenn die vordefinierten Instanzen des Typs vorhanden sind, deklarieren Sie diese als öffentliche schreibgeschützte statische Felder des Typs selbst.</span><span class="sxs-lookup"><span data-stu-id="78f63-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="78f63-115">**X nicht** Zuweisen von Instanzen von Typen, die auf änderbare `readonly` Felder.</span><span class="sxs-lookup"><span data-stu-id="78f63-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="78f63-116">Ein änderbarer Typ ist ein Typ mit Instanzen, die geändert werden können, nachdem sie instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="78f63-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="78f63-117">Z. B. Arrays, die meisten Auflistungen und Streams änderbare Typen sind jedoch <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, und <xref:System.String?displayProperty=nameWithType> sind alle unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="78f63-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="78f63-118">Den schreibgeschützten Modifizierer auf einen Typ Verweisfeld wird verhindert, dass die Instanz, die in das Feld ersetzt wird gespeichert, aber es verhindert jedoch nicht das Feld Instanzdaten bearbeitet werden durch Aufrufen von Membern die Instanz ändern.</span><span class="sxs-lookup"><span data-stu-id="78f63-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="78f63-119">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="78f63-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="78f63-120">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="78f63-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f63-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78f63-121">See Also</span></span>  
 [<span data-ttu-id="78f63-122">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="78f63-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="78f63-123">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="78f63-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
