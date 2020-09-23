---
title: Generische Typen
ms.date: 07/20/2015
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
ms.openlocfilehash: f9b343c664baaf316e5cd6df72da8dcf56222382
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090260"
---
# <a name="generic-types-in-visual-basic-visual-basic"></a>Generische Typen in Visual Basic (Visual Basic)

Ein *generischer Typ* ist ein einzelnes Programmierelement, das sich so anpasst, dass es für verschiedene Datentypen dieselben Funktionalität ausführt. Wenn Sie eine generische Klasse oder Prozedur definieren, müssen Sie keine separate Version für jeden Datentyp definieren, für den Sie diese Funktionalität möglicherweise ausführen möchten.  
  
 Eine Analogie hierzu ist ein Schraubendrehersatz mit auswechselbaren Spitzen. Sie sehen sich die Schraube an, die Sie drehen müssen, und wählen die geeignete Spitze für diese Schraube aus (geschlitzt, gekreuzt oder mit Stern). Sobald Sie die richtige Spitze in den Schraubendreher gesteckt haben, führen Sie mit dem Schraubendreher genau diese Funktion aus, d. h., Sie drehen die Schraube.  
  
 ![Diagramm eines Schraubendreher Satzes mit unterschiedlichen Köpfen.](./media/generic-types/generic-screwdriver-set.gif)  
  
 Wenn Sie einen generischen Typ definieren, parametrisieren Sie ihn mit mindestens einem Datentyp. Dies ermöglicht es, die Datentypen mithilfe von Code an die Anforderungen anzupassen. Im Code können Sie mehrere unterschiedliche Programmierelemente anhand des generischen Elements deklarieren, von denen jedes für eine andere Gruppe von Datentypen ausgeführt wird. Die deklarierten Elemente führen jedoch alle dieselbe Logik aus, unabhängig davon, welche Datentypen von ihnen verwendet werden.  
  
 Nehmen Sie beispielsweise an, Sie möchten eine Warteschlangeklasse erstellen und verwenden, die für einen bestimmten Datentyp, z. B. `String`, ausgeführt wird. Sie können eine solche Klasse über <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>deklarieren, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#1)]  
  
 Nun können Sie `stringQ` verwenden, um ausschließlich mit `String` -Werten zu arbeiten. Da `stringQ` speziell für `String` -Werte und nicht allgemein für `Object` -Werte verwendet wird, gibt es weder späte Bindung noch Typkonvertierung. Dies erspart Ausführungszeit und verringert Laufzeitfehler.  
  
 Weitere Informationen zur Verwendung eines generischen Typs finden Sie unter [How to: Use a Generic Class](how-to-use-a-generic-class.md).  
  
## <a name="example-of-a-generic-class"></a>Beispiel für eine generische Klasse  

 Im folgenden Beispiel wird eine Rumpfdefinition einer generischen Klasse veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#2)]  
  
 Im dieser Rumpfdefinition ist `t` ein *Typparameter*, d. h. ein Platzhalter für einen Datentyp, den Sie beim Deklarieren der Klasse angeben. An anderer Stelle im Code können Sie verschiedene Versionen von `classHolder` deklarieren, indem Sie für `t`verschiedene Datentypen angeben. Im folgenden Beispiel werden zwei solcher Deklarationen gezeigt.  
  
 [!code-vb[VbVbalrDataTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#3)]  
  
 Die vorangehenden Anweisungen deklarieren *konstruierte Klassen*, in denen ein bestimmter Typ den Typparameter ersetzt. Diese Ersetzung wird im gesamten Code in der konstruierten Klasse weitergegeben. Im folgenden Beispiel wird gezeigt, wie die `processNewItem` -Prozedur in `integerClass`aussieht.  
  
 [!code-vb[VbVbalrDataTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#4)]  
  
 Ein ausführlichere Beispiel finden Sie unter Gewusst [wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](how-to-define-a-class-that-can-provide-identical-functionality.md).  
  
## <a name="eligible-programming-elements"></a>Geeignete Programmierelemente  

 Sie können generische Klassen, Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden. Beachten Sie, dass der .NET Framework mehrere generische Klassen, Strukturen und Schnittstellen definiert, die häufig verwendete generische Elemente darstellen. Der <xref:System.Collections.Generic?displayProperty=nameWithType> -Namespace stellt Wörterbücher, Listen, Warteschlangen und Stapel bereit. Bevor Sie ein eigenes generisches Element definieren, überprüfen Sie, ob es bereits in <xref:System.Collections.Generic?displayProperty=nameWithType>verfügbar ist.  
  
 Prozeduren sind keine Typen, Sie können aber generische Prozeduren definieren und verwenden. Siehe [Generic Procedures in Visual Basic](generic-procedures.md).  
  
## <a name="advantages-of-generic-types"></a>Vorteile von generischen Typen  

 Ein generischer Typ fungiert als Basis für das Deklarieren mehrerer unterschiedlicher Programmierelemente, von denen jedes für einen bestimmten Datentyp ausgeführt wird. Die Alternativen zu einem generischen Typ sind:  
  
1. Ein einzelner Typ, der auf den `Object` -Datentyp angewendet wird.  
  
2. Ein Satz von *typspezifischen* Versionen des Typs, wobei jede Version einzeln codiert ist und auf einem bestimmten Datentyp, z `String` `Integer` . b., oder einem benutzerdefinierten Typ, wie z. b., ausgeführt wird `customer` .  
  
 Ein generischer Typ bietet folgende Vorteile gegenüber diesen Alternativen:  
  
- **Typsicherheit.** . Generische Typen erzwingen die Typüberprüfung zur Kompilierzeit. Auf `Object` basierende Typen akzeptieren jeden Datentyp, und Sie müssen Code schreiben, der überprüft, ob ein Eingabedatentyp zulässig ist. Mit generischen Typen kann der Compiler Typenkonflikte vor der Laufzeit abfangen.  
  
- **Leistung** Generische Typen müssen kein *Boxing* und *unBoxing* für Daten ausführen, da jeder Typ speziell für einen Datentyp verwendet wird. Operationen, die auf `Object` basierend, müssen für Eingabedatentypen Boxing ausführen, um sie in `Object` zu konvertieren, und Unboxing für Daten ausführen, die für die Ausgabe vorgesehen sind. Durch Boxing und Unboxing wird die Leistung verringert.  
  
     Typen, die auf `Object` basieren, sind außerdem spät gebunden, d. h., dass der Zugriff auf ihre Member zusätzlichen Code zur Laufzeit erfordert. Hierdurch wird die Leistung ebenfalls verringert.  
  
- **Codekonsolidierung.** Der Code in einem generischen Typ muss nur einmal definiert werden. Ein Satz typspezifischer Versionen eines Typs muss in jeder Version denselben Code replizieren, wobei der einzige Unterschied im speziellen Datentyp für die jeweilige Version besteht. Bei generischen Typen werden alle typspezifischen Versionen aus dem ursprünglichen generischen Typ generiert.  
  
- **Wiederverwendung von Code** . Code, der nicht von einem bestimmten Datentyp abhängt, kann für verschiedene Datentypen wiederverwendet werden, wenn er generisch ist. Sie können ihn häufig sogar für einen Datentypen wiederverwenden, den Sie ursprünglich nicht vorausbestimmt haben.  
  
- **IDE-Unterstützung.** Wenn Sie einen konstruierten Typ verwenden, der aus einem generischen Typ deklariert wurde, können Sie durch die IDE (Integrated Development Environment, integrierte Entwicklungsumgebung) weitere Unterstützung beim Verfassen des Codes erhalten. Beispielsweise kann IntelliSense Ihnen die typspezifischen Optionen für ein Argument eines Konstruktors oder einer Methode anzeigen.  
  
- **Generische Algorithmen.** Abstrakte Algorithmen, die typunabhängig sind, sind gute Kandidaten für generische Typen. Beispielsweise kann eine generische Prozedur, die Elemente mithilfe der <xref:System.IComparable> -Schnittstelle sortiert, für jeden Datentyp verwendet werden, der <xref:System.IComparable>implementiert.  
  
## <a name="constraints"></a>Einschränkungen  

 Obwohl der Code in der Definition eines generischen Typs so typunabhängig wie möglich sein sollte, müssen Sie eventuell eine bestimmte Fähigkeit irgendeines Datentyps erfordern, der dem generischen Datentyp bereitgestellt wird. Wenn Sie z. B. zwei Elemente vergleichen möchten, um sie zu sortieren oder abzugleichen, muss ihr Datentyp die <xref:System.IComparable> -Schnittstelle implementieren. Sie können diese Anforderung erzwingen, indem Sie dem Typparameter eine *Einschränkung* hinzufügen.  
  
### <a name="example-of-a-constraint"></a>Beispiel für eine Einschränkung  

 Im folgenden Beispiel wird die Rumpfdefinition einer Klasse mit einer Einschränkung gezeigt, die für das Typargument erfordert, dass es <xref:System.IComparable>implementiert.  
  
 [!code-vb[VbVbalrDataTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#5)]  
  
 Wird in späterem Code versucht, eine Klasse aus `itemManager` zu erstellen, wozu ein Typ bereitgestellt wird, der <xref:System.IComparable>nicht implementiert, signalisiert der Compiler einen Fehler.  
  
### <a name="types-of-constraints"></a>Typen von Einschränkungen  

 In einer Einschränkung können die folgenden Anforderungen in beliebiger Kombination angegeben werden:  
  
- Das Typargument muss mindestens eine Schnittstelle implementieren.  
  
- Das Typargument darf nur den Typ einer einzigen Klasse haben oder von einer einzigen Klasse erben.  
  
- Das Typargument muss einen parameterlosen Konstruktor für den Code verfügbar machen, der Objekte aus dem Typargument erstellt.  
  
- Das Typargument muss ein *Verweistyp*sein, oder es muss ein *Werttyp* sein.  
  
 Wenn Sie mehrere Einschränkungen erzwingen müssen, verwenden Sie eine durch Trennzeichen getrennte *Einschränkungsliste* in geschweiften Klammern (`{ }`). Wenn Sie einen barrierefreien Konstruktor benötigen, fügen Sie das [neue Operator](../../../language-reference/operators/new-operator.md) Schlüsselwort in die Liste ein. Um festzulegen, dass ein Verweistyp erforderlich ist, fügen Sie das `Class` -Schlüsselwort ein. Um festzulegen, dass ein Werttyp erforderlich ist, fügen Sie das `Structure` -Schlüsselwort ein.  
  
 Weitere Informationen über Einschränkungen finden Sie unter [Type List](../../../language-reference/statements/type-list.md).  
  
### <a name="example-of-multiple-constraints"></a>Beispiel für mehrere Einschränkungen  

 Im folgenden Beispiel wird die Rumpfdefinition einer generischen Klasse mit einer Einschränkungsliste für den Typparameter veranschaulicht. In dem Code, der eine Instanz dieser Klasse erstellt, muss das Typargument sowohl die <xref:System.IComparable> -Schnittstelle als auch die <xref:System.IDisposable> -Schnittstelle implementieren, ein Verweistyp sein und einen zugänglichen parameterlosen Konstruktor verfügbar machen.  
  
 [!code-vb[VbVbalrDataTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#6)]  
  
## <a name="important-terms"></a>Wichtige Begriffe  

 Für generische Typen werden die folgenden Begriffe verwendet:  
  
- *Generischer Typ*. Eine Definition einer Klasse, einer Struktur, einer Schnittstelle, einer Prozedur oder eines Delegaten, für deren bzw. dessen Deklaration Sie mindestens einen Datentyp angeben.  
  
- *Typparameter*. In der Definition eines generischen Typs ein Platzhalter für einen Datentyp, den Sie beim Deklarieren des Typs angeben.  
  
- *Typargument*. Ein spezieller Datentyp, der einen Typparameter ersetzt, wenn Sie einen konstruierten Typ aus einem generischen Typ deklarieren.  
  
- *Einschränkung*. Eine Bedingung für einen Typparameter, die das Typargument einschränkt, das Sie für den Typparameter angeben können. Eine Einschränkung kann festlegen, dass das Typargument eine bestimmte Schnittstelle implementieren, eine bestimmte Klasse sein oder von einer bestimmten Klasse erben, einen zugänglichen parameterlosen Konstruktor haben oder ein Verweistyp oder ein Werttyp sein muss. Sie können diese Einschränkungen kombinieren, Sie können aber maximal eine Klasse angeben.  
  
- *Konstruierter Typ*. Eine Klasse, eine Struktur, eine Schnittstelle, eine Prozedur oder ein Delegat, die bzw. der aus einem generischen Typ deklariert wird, indem Typargumente für dessen Typparameter angegeben werden.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](index.md)
- [Typzeichen](type-characters.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Natürlich](../../../language-reference/statements/of-clause.md)
- [Möglichst](../../../language-reference/statements/as-clause.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Kovarianz und Kontravarianz](../../concepts/covariance-contravariance/index.md)
- [Iteratoren](../../concepts/iterators.md)
