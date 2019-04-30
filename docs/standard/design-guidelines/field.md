---
title: Feldentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 3ab8fe279605c4795bb3a26557d0241b186b273a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026405"
---
# <a name="field-design"></a><span data-ttu-id="abc3c-102">Feldentwurf</span><span class="sxs-lookup"><span data-stu-id="abc3c-102">Field Design</span></span>
<span data-ttu-id="abc3c-103">Das Prinzip der Kapselung ist eines der wichtigsten Konzepte in objektorientierten Entwurf.</span><span class="sxs-lookup"><span data-stu-id="abc3c-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="abc3c-104">Dieses Prinzip besagt, dass die Daten in ein Objekt nur dieses Objekt zugegriffen werden soll.</span><span class="sxs-lookup"><span data-stu-id="abc3c-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="abc3c-105">Eine gute Möglichkeit, das Prinzip zu interpretieren ist zu sagen, dass ein Typ sollten so konzipiert sein, dass Änderungen an Feldern dieses Typs (ändert sich Name oder Typ) erfolgen können, ohne Code, außer für Elemente des Typs.</span><span class="sxs-lookup"><span data-stu-id="abc3c-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="abc3c-106">Dieser Interpretation impliziert sofort, dass alle Felder privat sein müssen.</span><span class="sxs-lookup"><span data-stu-id="abc3c-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="abc3c-107">Wir schließen Konstanten und statische schreibgeschützte Felder aus dieser Einschränkung strict, da solche Felder per Definition fast nie ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="abc3c-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="abc3c-108">**X DO NOT** bieten Instanzfelder, die öffentlich und/oder geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="abc3c-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="abc3c-109">Für den Zugriff auf Felder anstelle von öffentlichen oder geschützten somit sollten Sie die Eigenschaften bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abc3c-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="abc3c-110">**✓ DO** verwenden Sie Konstante Felder für Konstanten, die nie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="abc3c-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="abc3c-111">Der Compiler nutzt die Werte der Konstanten, Felder direkt in Aufrufen von Code.</span><span class="sxs-lookup"><span data-stu-id="abc3c-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="abc3c-112">Aus diesem Grund können Konstante Werte ohne das Risiko der Unterbrechung der Kompatibilität nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="abc3c-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="abc3c-113">**✓ DO** öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen.</span><span class="sxs-lookup"><span data-stu-id="abc3c-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="abc3c-114">Wenn Sie vordefinierte Instanzen des Typs vorhanden sind, deklarieren Sie wie öffentliche schreibgeschützte statische Felder des Typs selbst.</span><span class="sxs-lookup"><span data-stu-id="abc3c-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="abc3c-115">**X DO NOT** Zuweisen von Instanzen von Typen, die auf änderbare `readonly` Felder.</span><span class="sxs-lookup"><span data-stu-id="abc3c-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="abc3c-116">Ein änderbarer Typ ist ein Typ mit Instanzen, die geändert werden kann, nachdem sie instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="abc3c-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="abc3c-117">Z. B. Arrays, die meisten Auflistungen und Streams veränderlicher Typen sind jedoch <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, und <xref:System.String?displayProperty=nameWithType> sind alle unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="abc3c-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="abc3c-118">Die schreibgeschützten Modifizierer auf einen Typ Referenzfeld wird verhindert, dass die Instanz, die in das Feld ersetzt wird gespeichert, aber es verhindert, dass Instanzdaten des Felds nicht geändert wird, durch Aufrufen von Membern die Instanz zu ändern.</span><span class="sxs-lookup"><span data-stu-id="abc3c-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="abc3c-119">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="abc3c-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="abc3c-120">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="abc3c-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc3c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abc3c-121">See also</span></span>

- [<span data-ttu-id="abc3c-122">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="abc3c-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="abc3c-123">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="abc3c-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
