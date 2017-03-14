---
title: "Zugriffsmodifizierer (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zugriffsmodifizierer [C#], Informationen über"
  - "Die Programmiersprache C#, Zugriffsmodifizierer"
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# Zugriffsmodifizierer (C#-Programmierhandbuch)
Alle Typen und Typmember verfügen über eine Zugriffsebene, durch die festgelegt wird, ob sie von anderem Code in der Assembly oder anderen Assemblys verwendet werden können.  Sie können die folgenden Zugriffsmodifizierer verwenden, um die Barrierefreiheit eines Typs oder Members anzugeben, wenn Sie ihn deklarieren:  
  
 [public](../../../csharp/language-reference/keywords/public.md)  
 Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.  
  
 [private](../../../csharp/language-reference/keywords/private.md)  
 Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder Struktur zugegriffen werden.  
  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 Auf den Typ oder Member kann nur von Code in derselben Klasse oder Struktur oder in einer Klasse zugegriffen werden, die von dieser Klasse abgeleitet ist.  
  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.  
  
 `protected internal`  
 Auf den Typ oder Member kann von jedem Code in der Assembly, in der er deklariert ist, oder von einer abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.  Der Zugriff von einer anderen Assembly muss innerhalb einer Klassendeklaration erfolgen, die von der Klasse abgeleitet wird, in der das geschützte interne Element deklariert wird, und er muss mithilfe einer Instanz des Typs der abgeleiteten Klasse erfolgen.  
  
 In den folgenden Beispielen wird veranschaulicht, wie Zugriffsmodifizierer für einen Typ und einen Member festgelegt werden:  
  
 [!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]  
  
 Je nach Typ, Member und Kontext können nicht alle Zugriffsmodifizierer verwendet werden. In verschiedenen Fällen wird der Zugriff für einen Typmember durch die Zugriffmöglichkeiten des enthaltenen Typs eingeschränkt.  Die folgenden Abschnitte enthalten weitere Details zu Zugriffsmöglichkeiten.  
  
## Verfügbarkeit von Klassen und Strukturen  
 Klassen und Strukturen, die innerhalb eines Namespace direkt deklariert werden \(d. h., sie sind nicht in anderen Klassen oder Strukturen geschachtelt\), haben entweder die Zugriffsebene public oder internal.  Wenn kein Zugriffsmodifizierer angegeben ist, wird standardmäßig internal verwendet.  
  
 Strukturmember, einschließlich geschachtelter Klassen und Strukturen, können als öffentlich, intern oder privat deklariert werden.  Klassenmember, einschließlich geschachtelter Klassen und Strukturen, können öffentlich, geschützt internes, geschützt, intern oder privat sein.  Die Zugriffsebene für Klassenmember und Strukturmember, einschließlich geschachtelter Klassen und Strukturen, ist standardmäßig privat.  Auf private geschachtelte Typen kann außerhalb des enthaltenden Typs nicht zugegriffen werden.  
  
 Abgeleitete Klassen können keine höhere Zugriffsebene haben als ihre Basistypen.  Sie können also keine öffentliche Klasse `B` von einer internen Klasse `A` ableiten.  Wenn dies zulässig wäre, würde die Zugriffsebene von `A` auf public festgelegt, da auf alle geschützten oder internen Member von `A` von der abgeleiteten Klasse aus zugegriffen werden kann.  
  
 Sie können bestimmte andere Assemblys aktivieren, um mithilfe des InternalsVisibleTo\-Attributs auf die internen Typen zuzugreifen.  Weitere Informationen finden Sie unter [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Verfügbarkeit von Klassen\- und Strukturmembern  
 Klassenmember \(einschließlich geschachtelter Klassen und Strukturen\) können mit jedem der fünf Zugriffstypen deklariert werden.  Strukturmember können nicht als protected deklariert werden, da Strukturen keine Vererbung unterstützen.  
  
 Normalerweise ist die Barrierefreiheit eines Members nicht größer als die Barrierefreiheit des Typs, der ihn enthält.  Allerdings kann auf einen öffentlichen Member einer internen Klasse von außerhalb der Assembly zugegriffen werden, wenn der Member Schnittstellenmethoden implementiert oder virtuelle Methoden überschreibt, die in einer öffentlichen Basisklasse definiert sind.  
  
 Der Typ eines Members, der ein Feld, eine Eigenschaft oder ein Ereignis darstellt, muss mindestens genauso verfügbar sein wie der Member selbst.  Entsprechend müssen der Rückgabetyp und die Parametertypen eines Members, der eine Methode, Indexer oder Delegat ist, mindestens genauso verfügbar sein wie der Member selbst.  Eine öffentliche Methode `M` kann beispielsweise nur dann eine Klasse `C` zurückgeben, wenn `C` ebenfalls über die Zugriffsebene public verfügt.  Entsprechend können Sie nicht über eine geschützte Eigenschaft des Typs `A` verfügen, wenn `A` als private deklariert wurde.  
  
 Benutzerdefinierte Operatoren müssen immer als public deklariert werden.  Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).  
  
 Destruktoren können nicht über Zugriffsmodifizierer verfügen.  
  
 Um die Zugriffsebene für einen Klassen\- oder Strukturmember festzulegen, fügen Sie das entsprechende Schlüsselwort der Memberdeklaration hinzu, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]  
  
> [!NOTE]
>  Die Zugriffsebene protected internal bedeutet protected ODER internal, nicht protected UND internal.  Anders ausgedrückt kann auf einen geschützten internen Member aus einer Klasse in derselben Assembly, einschließlich abgeleiteter Klassen, zugegriffen werden.  Wenn Sie den Zugriff auf abgeleitete Klassen in derselben Assembly beschränken möchten, deklarieren Sie die Klasse selbst als internal und ihre Member als protected.  
  
## Weitere Typen  
 Schnittstellen, die direkt in einem Namespace deklariert werden, können als public oder internal deklariert werden. Wie bei Klassen und Strukturen ist der Standardzugriff von Schnittstellen internal.  Schnittstellenmember sind stets public, da es die Funktion einer Schnittstelle ist, anderen Typen Zugriff auf eine Klasse oder Struktur zu ermöglichen.  Auf Schnittstellenmember können keine Zugriffsmodifizierer angewendet werden.  
  
 Enumerationsmember sind immer public, und Zugriffsmodifizierer sind nicht erlaubt.  
  
 Delegaten verhalten sich wie Klassen und Strukturen.  Standardmäßig haben sie internen Zugriff bei direkter Deklarierung in einem Namespace und privaten Zugriff bei Schachtelung.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [Private](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [Klasse](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [Schnittstelle](../../../csharp/language-reference/keywords/interface.md)