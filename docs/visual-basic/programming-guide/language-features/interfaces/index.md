---
title: Schnittstellen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, interfaces
- interfaces, Visual Basic
- interfaces
- interfaces [Visual Basic]
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: a95f3cfc8213c6a34953ae3ce87c6f5da9c0f8ca
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
<a id="interfaces-visual-basic" class="xliff"></a>

# Schnittstellen (Visual Basic)
*Schnittstellen* definieren die Eigenschaften, Methoden und Ereignisse, die von Klassen implementiert werden können. Schnittstellen erlauben es Ihnen, Funktionen als kleine Gruppen mit verwandten Eigenschaften, Methoden und Ereignisse zu definieren. Dadurch werden Kompatibilitätsprobleme reduziert, da Sie für die Schnittstellen erweiterte Implementierungen entwickeln können, ohne vorhandenen Code zu gefährden. Sie können neue Funktionen zu einem beliebigen Zeitpunkt hinzufügen, indem Sie weitere Schnittstellen und Implementierungen entwickeln.  
  
 Es gibt viele weitere Gründe, warum Sie möglicherweise Schnittstellen anstelle der Klassenvererbung verwenden möchten:  
  
-   Schnittstellen sind besser für Situationen geeignet, in denen Anwendungen viele nicht verknüpfte Objekttypen erfordern, um bestimmte Funktionen bereitzustellen.  
  
-   Schnittstellen sind flexibler als Basisklassen, da Sie eine einzelne Implementierung definieren können, die mehrere Schnittstellen implementieren kann.  
  
-   Schnittstellen sind in Situationen vorzuziehen, in denen Sie keine Implementierung von einer Basisklasse erben.  
  
-   Schnittstellen sind nützlich, wenn Sie keine Klassenvererbung verwenden können. Z. B. Strukturen können nicht von Klassen erben, sie können jedoch Schnittstellen implementieren.  
  
<a id="declaring-interfaces" class="xliff"></a>

## Deklarieren von Schnittstellen  
 Schnittstellendefinitionen werden innerhalb der `Interface` und `End Interface` Anweisungen eingeschlossen. Nach der `Interface` Anweisung können Sie eine optionale `Inherits` Anweisung hinzufügen, die eine oder mehrere geerbte Schnittstellen auflistet. Die `Inherits` Anweisungen müssen in der Deklaration vor allen anderen Anweisungen, außer Kommentaren, stehen. Die übrigen Anweisungen der Schnittstellendefinition sollten `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure`, und `Enum` Anweisungen sein. Schnittstellen können keinen Implementierungscode oder Anweisungen, die Implementierungscode zugeordnet sind, enthalten, wie z. B. `End Sub` oder `End Property`.  
  
 In einem Namespace sind Schnittstellenanweisungen standardmäßig `Friend`, aber sie können auch explizit als `Public` oder `Friend` deklariert sein. Schnittstellen, die innerhalb von Klassen, Modulen, Schnittstellen und Strukturen definiert sind, sind standardmäßig `Public`, können aber auch explizit als `Public`, `Friend`, `Protected`, oder `Private` deklariert sein.  
  
> [!NOTE]
>  Das `Shadows` Schlüsselwort kann auf alle Schnittstellenmember angewendet werden. Das `Overloads` Schlüsselwort kann bei `Sub`, `Function`, und `Property` Anweisungen angewendet werden und wird in der Schnittstellendefinition deklariert. Darüber hinaus können `Property` Anweisungen die `Default`, `ReadOnly`, oder `WriteOnly` Modifizierer haben. Alle anderen Modifizierer –`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride`, oder `Overridable`– sind zulässig. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Im folgende Code wird beispielsweise eine Schnittstelle mit einer Funktion, eine Eigenschaft und ein Ereignis definiert.  
  
 [!code-vb[VbVbalrOOP#17](../../../../visual-basic/misc/codesnippet/VisualBasic/index_1.vb)]  
  
<a id="implementing-interfaces" class="xliff"></a>

## Implementieren von Schnittsellen  
 Das [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] reservierte Wort `Implements` wird in zwei Arten verwendet. Die `Implements` Anweisung gibt an, dass eine Klasse oder Struktur eine Schnittstelle implementiert. Das `Implements` Schlüsselwort gibt an, dass ein Klassenmember oder ein Strukturmember ein bestimmtes Schnittstellenmember implementiert.  
  
<a id="implements-statement" class="xliff"></a>

### Implements-Anweisung  
 Wenn eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert, muss die `Implements` Anweisung unmittelbar nach der `Class` oder `Structure` Anweisung erfolgen. Die `Implements` Anweisung erfordert eine durch Trennzeichen getrennte Liste mit Schnittstellen, die von einer Klasse implementiert werden. Die Klasse oder Struktur muss alle Schnittstellenmember mit dem `Implements` Schlüsselwort implementieren.  
  
<a id="implements-keyword" class="xliff"></a>

### Implements-Schlüsselwort  
 Das `Implements` Schlüsselwort erfordert eine durch Trennzeichen getrennte Liste mit Schnittstellenmembern, die implementiert werden. In der Regel wird nur ein einziger Schnittstellenmember angegeben, aber Sie können mehrere Members angeben. Die Spezifikation eines Schnittstellenmembers besteht aus dem Schnittstellennamen, der in einer Implementierungsanweisung innerhalb der Klasse angegeben werden muss, einem Zeitraum und dem Namen der Memberfunktion, der Eigenschaft oder des Ereignisses, das implementiert werden soll. Der Name des Members, der ein Schnittstellenmember implementiert, kann jeden beliebigen zulässigen Bezeichner verwenden; und es gibt keine Beschränkung auf die `InterfaceName_MethodName` Konvention, die in früheren Versionen von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwendet wurde.  
  
 Der folgende Code zeigt z. B. das Deklarieren einer Unterroutine namens `Sub1`, die eine Methode einer Schnittstelle implementiert:  
  
 [!code-vb[VbVbalrOOP#69](../../../../visual-basic/misc/codesnippet/VisualBasic/index_2.vb)]  
  
 Die Parametertypen und Rückgabetypen des implementierenden Members müssen mit den Schnittstelleneigenschaften oder der Memberdeklaration in der Schnittstelle übereinstimmen. Die gängigste Methode, um ein Element in einer Schnittstelle zu implementieren, ist mit einem Element, das den gleichen Namen wie die Schnittstelle hat, wie im vorherigen Beispiel gezeigt.  
  
 Zum Deklarieren der Implementierung einer Schnittstellenmethode können Sie alle Attribute verwenden, die für Deklarationen von Instanzenmethoden, einschließlich `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default`, und `Static` zulässig sind. Das `Shared` Attribut ist nicht zulässig, da es keine Instanzmethode, sondern eine Klasse definiert.  
  
 Mithilfe von `Implements`, können Sie auch eine einzelne Methode schreiben, die mehrere Methoden  implementiert, die in einer Schnittstelle definiert sind, wie z. B.:  
  
 [!code-vb[VbVbalrOOP#70](../../../../visual-basic/misc/codesnippet/VisualBasic/index_3.vb)]  
  
 Sie können einen privaten Member verwenden, um ein Schnittstellenmember zu implementieren. Wenn ein privater Member einen Member einer Schnittstelle implementiert, wird dieses Member durch die Schnittstelle verfügbar, obwohl er nicht direkt in Objektvariablen für die Klasse verfügbar ist.  
  
<a id="interface-implementation-examples" class="xliff"></a>

### Beispiele für Schnittstellenimplementierung  
 Klassen, die eine Schnittstelle implementieren, müssen alle Eigenschaften, Methoden und Ereignisse implementieren.  
  
 Im folgenden Beispiel werden zwei Schnittstellen definiert. Die zweite Schnittstelle `Interface2`, erbt `Interface1` und definiert eine zusätzliche Eigenschaft und Methode.  
  
 [!code-vb[VbVbalrOOP#39](../../../../visual-basic/misc/codesnippet/VisualBasic/index_4.vb)]  
  
 Das nächste Beispiel implementiert `Interface1`, die im vorherigen Beispiel definierte Schnittstelle:  
  
 [!code-vb[VbVbalrOOP#40](../../../../visual-basic/misc/codesnippet/VisualBasic/index_5.vb)]  
  
 Das abschließende Beispiel implementiert `Interface2`, einschließlich einer Methode geerbt von `Interface1`:  
  
 [!code-vb[VbVbalrOOP#41](../../../../visual-basic/misc/codesnippet/VisualBasic/index_6.vb)]  
  
 Sie können eine schreibgeschützte Eigenschaft mit einer Readwrite-Eigenschaft implementieren (das heißt, Sie müssen sie nicht als schreibgeschützt in der implementierenden Klasse deklarieren).  Implementieren einer Schnittstelle verspricht mindestens die Member zu implementieren, die die Schnittstelle deklariert, aber Sie können mehr Funktionalität bieten, z. B. Schreibbarkeit Ihrer Eigenschaft.  
  
<a id="related-topics" class="xliff"></a>

## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/walkthrough-creating-and-implementing-interfaces.md)|Bietet eine ausführliche Anleitung, die Sie durch den Prozess des Definierens und Implementierens Ihrer eigenen Schnittstellen führt.|  
|[Varianz in generischen Schnittstellen](http://msdn.microsoft.com/library/e14322da-1db3-42f2-9a67-397daddd6b6a)|Erläutert Ko- und Kontravarianz in generischen Schnittstellen und enthält eine Liste der Varianten generischen Schnittstellen in .NET Framework.|
