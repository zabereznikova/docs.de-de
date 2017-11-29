---
title: Namen von Typmembern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1a3460b734d5bab6f5362fa9d3631e06821f6d49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-type-members"></a><span data-ttu-id="9f5bd-102">Namen von Typmembern</span><span class="sxs-lookup"><span data-stu-id="9f5bd-102">Names of Type Members</span></span>
<span data-ttu-id="9f5bd-103">Typen von Elementen vorgenommen werden: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="9f5bd-104">In den folgenden Abschnitten werden die Richtlinien für die Benennung von Typmembern beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="9f5bd-105">Namen von Methoden</span><span class="sxs-lookup"><span data-stu-id="9f5bd-105">Names of Methods</span></span>  
 <span data-ttu-id="9f5bd-106">Da Methoden überprüfbarer Aktionen sind, müssen die Entwurfsrichtlinien Methodennamen Verben oder verbale Ausdrücke sein.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="9f5bd-107">Befolgen diese Richtlinie auch dient zur Unterscheidung von Methodennamen aus den Namen der Eigenschaft, und geben die Nomen oder Adjektiv Ausdrücke sind.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="9f5bd-108">**Führen Sie ✓** Geben Sie einen Methodennamen, die Verben oder verbale Ausdrücke sind.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="9f5bd-109">Namen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9f5bd-109">Names of Properties</span></span>  
 <span data-ttu-id="9f5bd-110">Im Gegensatz zu anderen Mitgliedern Eigenschaften nominaler Ausdruck oder adjektivische Namen Unternehmensservern benötigen.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="9f5bd-111">Grund hierfür eine Eigenschaft bezieht sich auf Daten und der Namen der Eigenschaft angibt, ist.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="9f5bd-112">PascalCasing wird immer für Eigenschaftennamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="9f5bd-113">**Führen Sie ✓** Benennen von Eigenschaften, die über ein Nomen, nominaler Ausdruck oder Adjektiv.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="9f5bd-114">**X nicht** verfügen über Eigenschaften, die den Namen des "Get"-Methoden, wie im folgenden Beispiel entsprechen:</span><span class="sxs-lookup"><span data-stu-id="9f5bd-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="9f5bd-115">Dieses Muster gibt normalerweise an, dass die Eigenschaft wirklich ein Methode sein sollte.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="9f5bd-116">**Führen Sie ✓** benennen Sammlungseigenschaften mit einem im plural Ausdruck beschreiben die Elemente in der Auflistung anstatt im singular Ausdruck gefolgt von "List" oder "Collection".</span><span class="sxs-lookup"><span data-stu-id="9f5bd-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="9f5bd-117">**Führen Sie ✓** benennen boolesche Eigenschaften, die mit einem positiven Begriff (`CanSeek` anstelle von `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="9f5bd-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="9f5bd-118">Optional, Sie können auch das Präfix boolescher Eigenschaften, die mit "Is", "kann" oder "Hat," jedoch nur, sofern der Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="9f5bd-119">**✓ GGF.** erteilen einer Eigenschaft den gleichen Namen wie den Typ.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="9f5bd-120">Beispielsweise ruft die folgende Eigenschaft ordnungsgemäß und legt einen Enumerationswert, der mit dem Namen `Color`, sodass die Eigenschaft heißt `Color`:</span><span class="sxs-lookup"><span data-stu-id="9f5bd-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="9f5bd-121">Namen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="9f5bd-121">Names of Events</span></span>  
 <span data-ttu-id="9f5bd-122">Ereignisse beziehen sich immer auf eine Aktion aus, entweder ein Fehler oder eine, die aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="9f5bd-123">Daher wie bei Methoden, Ereignisse mit Verben heißen und Verb Zeitformen wird verwendet, um den Zeitpunkt angibt, wann das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="9f5bd-124">**Führen Sie ✓** benennen Sie Ereignisse mit einem Verb oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="9f5bd-125">Beispiele hierfür sind `Clicked`, `Painting`, `DroppedDown`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="9f5bd-126">**Führen Sie ✓** benennen Ereignisse Namen durch ein Konzept von vor und nach, mit der vorhanden und der Vergangenheit Zeitformen.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="9f5bd-127">Beispielsweise würde ein Schließen-Ereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird aufgerufen werden `Closing`, und eine, die ausgelöst wird, nachdem das Fenster geschlossen wird aufgerufen `Closed`.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="9f5bd-128">**X nicht** "Before" oder "After"-Präfixe oder Suffixe an, dass vor und nach der Ereignisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="9f5bd-129">Verwenden Sie vorhanden und Vergangenheit Zeitformen wie gerade beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="9f5bd-130">**Führen Sie ✓** Ereignishandlerauflistung (Delegaten als Typen von Ereignissen verwendet) mit dem Suffix "EventHandler" nennen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9f5bd-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="9f5bd-131">**Führen Sie ✓** verwenden zwei Parameter mit dem Namen `sender` und `e` in den Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="9f5bd-132">Der Parameter Sender stellt das Objekt, das das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="9f5bd-133">Der Absenderparameter ist in der Regel vom Typ `object`, selbst wenn es möglich ist, einen spezifischeren Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="9f5bd-134">**Führen Sie ✓** benennen Sie Ereignisargumentklassen mit dem Suffix "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="9f5bd-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="9f5bd-135">Namen von Feldern</span><span class="sxs-lookup"><span data-stu-id="9f5bd-135">Names of Fields</span></span>  
 <span data-ttu-id="9f5bd-136">Die Benennung von Feld-Richtlinien gelten für statische öffentliche und geschützte Felder.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="9f5bd-137">Interne und private Felder werden nicht behandelt, durch die Richtlinien und öffentlichen oder geschützten Instanzfelder sind nicht zulässig, durch die [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="9f5bd-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="9f5bd-138">**Führen Sie ✓** PascalCasing in Feldnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="9f5bd-139">**Führen Sie ✓** Namen von Feldern an, indem ein Nomen, nominaler Ausdruck oder Adjektiv.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="9f5bd-140">**X nicht** verwenden Sie ein Präfix für Feldnamen.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="9f5bd-141">Verwenden Sie z. B. nicht "G_" oder "S_" an, dass statische Felder.</span><span class="sxs-lookup"><span data-stu-id="9f5bd-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="9f5bd-142">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="9f5bd-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9f5bd-143">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="9f5bd-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5bd-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f5bd-144">See Also</span></span>  
 [<span data-ttu-id="9f5bd-145">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9f5bd-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="9f5bd-146">Benennungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9f5bd-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
