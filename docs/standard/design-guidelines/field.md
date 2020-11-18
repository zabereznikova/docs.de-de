---
title: Feldentwurf
ms.date: 10/22/2008
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 6e58274f32ea129d3271c11e321bdbd454d2406a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821111"
---
# <a name="field-design"></a><span data-ttu-id="73d36-102">Feldentwurf</span><span class="sxs-lookup"><span data-stu-id="73d36-102">Field Design</span></span>
<span data-ttu-id="73d36-103">Das Prinzip der Kapselung ist einer der wichtigsten Begriffe im objektorientierten Entwurf.</span><span class="sxs-lookup"><span data-stu-id="73d36-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="73d36-104">Dieses Prinzip gibt an, dass auf Daten, die in einem Objekt gespeichert sind, nur dieses Objekt zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="73d36-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>

 <span data-ttu-id="73d36-105">Eine gute Möglichkeit, das Prinzip zu interpretieren, besteht darin zu sagen, dass ein Typ so entworfen werden sollte, dass Änderungen an Feldern dieses Typs (Name oder Typänderungen) ohne einen anderen Code als für Member des Typs vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="73d36-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="73d36-106">Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.</span><span class="sxs-lookup"><span data-stu-id="73d36-106">This interpretation immediately implies that all fields must be private.</span></span>

 <span data-ttu-id="73d36-107">Wir schließen Konstante und statische schreibgeschützte Felder aus dieser strikten Einschränkung aus, da solche Felder, fast definitionsgemäß, niemals geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="73d36-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>

 <span data-ttu-id="73d36-108">❌ Stellen Sie keine Instanzfelder bereit, die öffentlich oder geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="73d36-108">❌ DO NOT provide instance fields that are public or protected.</span></span>

 <span data-ttu-id="73d36-109">Sie sollten Eigenschaften für den Zugriff auf Felder bereitstellen, anstatt sie öffentlich oder geschützt zu machen.</span><span class="sxs-lookup"><span data-stu-id="73d36-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>

 <span data-ttu-id="73d36-110">✔️ verwenden Konstante Felder für Konstanten, die sich nie ändern.</span><span class="sxs-lookup"><span data-stu-id="73d36-110">✔️ DO use constant fields for constants that will never change.</span></span>

 <span data-ttu-id="73d36-111">Der Compiler verbrennt die Werte der Konstanten Felder direkt in aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="73d36-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="73d36-112">Daher können Konstanten Werte nie geändert werden, ohne dass die Kompatibilität unterbrochen werden muss.</span><span class="sxs-lookup"><span data-stu-id="73d36-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>

 <span data-ttu-id="73d36-113">✔️ öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="73d36-113">✔️ DO use public static `readonly` fields for predefined object instances.</span></span>

 <span data-ttu-id="73d36-114">Wenn vordefinierte Instanzen des-Typs vorhanden sind, deklarieren Sie Sie als öffentliche schreibgeschützte statische Felder des Typs selbst.</span><span class="sxs-lookup"><span data-stu-id="73d36-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>

 <span data-ttu-id="73d36-115">❌ Weisen Sie Feldern keine Instanzen von änderbaren Typen zu `readonly` .</span><span class="sxs-lookup"><span data-stu-id="73d36-115">❌ DO NOT assign instances of mutable types to `readonly` fields.</span></span>

 <span data-ttu-id="73d36-116">Ein änderbarer Typ ist ein Typ mit-Instanzen, die geändert werden können, nachdem Sie instanziiert wurden.</span><span class="sxs-lookup"><span data-stu-id="73d36-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="73d36-117">Arrays, die meisten Auflistungen und Streams sind z. b. änderbare Typen, aber <xref:System.Int32?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> und <xref:System.String?displayProperty=nameWithType> sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="73d36-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="73d36-118">Der schreibgeschützte Modifizierer in einem Verweistyp Feld verhindert, dass die im Feld gespeicherte Instanz ersetzt wird, aber verhindert, dass die Instanzdaten des Felds durch Aufrufen von Membern, die die Instanz ändern, geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73d36-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>

 <span data-ttu-id="73d36-119">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="73d36-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="73d36-120">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="73d36-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="73d36-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73d36-121">See also</span></span>

- [<span data-ttu-id="73d36-122">Entwurfs Richtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="73d36-122">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="73d36-123">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="73d36-123">Framework Design Guidelines</span></span>](index.md)
