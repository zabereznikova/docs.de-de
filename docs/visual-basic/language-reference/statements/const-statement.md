---
title: Const-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 3d8134b43320003a6425cf284162d3d627b177c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623557"
---
# <a name="const-statement-visual-basic"></a>Const-Anweisung (Visual Basic)
Deklariert und definiert eine oder mehrere Konstanten.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Liste der Attribute, die für alle Konstanten gelten, die in dieser Anweisung deklariert werden. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").  
  
 `accessmodifier`  
 Dies ist optional. Verwenden Sie diese Option, um anzugeben, welcher Code auf diese Konstanten zugreifen kann. Kann [öffentliche](../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), oder [Privat geschützt](../../language-reference/modifiers/private-protected.md).
  
 `Shadows`  
 Dies ist optional. Hiermit können Sie Sie deklarieren und ein Programmierelement ein Element in einer Basisklasse auszublenden. Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Erforderlich. Liste von Konstanten, die in dieser Anweisung deklariert wird.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Jede `constant` weist folgende Syntax und Bestandteile auf:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`constantname`|Erforderlich. Die Namen der Konstanten. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp der Konstante.|  
|`initializer`|Erforderlich. Ausdruck, der zur Kompilierzeit ausgewertet, und der Konstante zugewiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn sich einen Wert, der sich nie ändert, in Ihrer Anwendung, können Sie eine benannte Konstante zu definieren und verwenden sie statt eines Literalwerts. Ein Name ist leichter zu merken als einen Wert. Sie können die Konstante nur einmal definieren und an vielen Stellen in Ihrem Code verwenden. Wenn in einer späteren Version Sie den Wert neu definieren müssen die `Const` Anweisung ist der einzige Ort, die Sie ändern möchten.  
  
 Sie können `Const` nur auf Module oder Prozedur. Dies bedeutet, dass die *Deklarationskontext* für eine Variable, eine Klasse, Struktur, Modul, Prozedur oder Block sein muss, und eine Quelldatei, Namespace oder Schnittstelle nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Lokale Konstanten (innerhalb einer Prozedur) standardmäßig öffentlichen Zugriff, und Sie können keine Zugriffsmodifizierer darauf. Klasse Konstanten (außerhalb einer Prozedur) standardmäßig und in privaten Zugriff und Struktur Member standardmäßig öffentlichen Zugriff auf Konstanten. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Eine Konstante deklariert, auf Modulebene außerhalb einer Prozedur, wird eine *Memberkonstante*; es ist ein Member der Klasse, Struktur oder Modul deklariert, die es.  
  
     Eine Konstante, die auf Prozedurebene deklariert ist eine *lokale Konstante*; es lokal auf die Prozedur oder der Block, der sie deklariert ist.  
  
-   **Attribute.** Sie können Attribute anwenden, nur, Memberkonstanten, nicht für lokale Konstanten. Ein Attribut fügt Informationen an den Metadaten der Assembly, die hat keine Bedeutung für die temporäre Speicherung, z. B. lokale Konstanten.  
  
-   **Modifizierer.** Standardmäßig sind alle Konstanten `Shared`, `Static`, und `ReadOnly`. Sämtliche dieser Schlüsselwörter können keine beim Deklarieren einer Konstante.  
  
     Auf Prozedurebene, können keine `Shadows` Zugriffsmodifizierern zum Deklarieren von lokaler Konstanten.  
  
-   **Mehrere Konstanten.** Sie können mehrere Konstanten in der gleichen deklarationsanweisung deklarieren angeben der `constantname` für jeden einzelnen Teil. Mehrere Konstanten werden durch Kommas getrennt.  
  
## <a name="data-type-rules"></a>Daten – Typenregeln  
  
-   **Datentypen.** Die `Const` -Anweisung kann den Datentyp einer Variablen deklarieren. Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration angeben.  
  
-   **Standard-Typ.** Wenn Sie keinen angeben `datatype`, die Konstante hat den Datentyp der `initializer`. Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` müssen konvertierbar sein `datatype`. Wenn weder `datatype` noch `initializer` vorhanden ist, geben Sie die Daten standardmäßig `Object`.  
  
-   **Verschiedene Typen.** Sie können für unterschiedliche Konstanten unterschiedliche Datentypen angeben, über ein separates `As` -Klausel für jede Variable, die Sie deklarieren. Allerdings kann nicht deklariert werden mehrere Konstanten desselben Typs mit einer gemeinsamen `As` Klausel.  
  
-   **Die Initialisierung.** Sie müssen den Wert jedes Konstanten in initialisieren `constantlist`. Verwenden Sie `initializer` , geben Sie einen Ausdruck, der Konstante zugewiesen werden soll. Der Ausdruck kann eine beliebige Kombination aus Literalen, andere Konstanten, die bereits definiert sind und Enumerationsmember, die bereits definierte sein. Sie können arithmetische und logische Operatoren verwenden, zur Kombination dieser Elemente.  
  
     Sie können keine Variablen oder Funktionen in `initializer`. Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`. Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` -Argument, das zum Zeitpunkt der Kompilierung ausgewertet werden können.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Bereich.** Lokale Konstanten sind nur innerhalb ihrer Prozedur oder eines Blocks zugegriffen werden. Memberkonstanten sind an einer beliebigen Stelle innerhalb ihrer Klasse, Struktur oder Modul zugegriffen werden.  
  
-   **Qualifizierung.** Code außerhalb einer Klasse, Struktur oder eines Moduls muss qualifizieren eine Memberkonstante Namen durch den Namen der Klasse, Struktur, bzw. des Moduls. Code außerhalb einer Prozedur oder einem Block kann auf alle lokalen Konstanten in dieser Prozedur oder eines Blocks verweisen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Const` -Anweisung zum Deklarieren von Konstanten für die Verwendung anstelle von literalen Werten.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Wenn Sie eine Konstante mit dem Datentyp definieren `Object`, Visual Basic-Compiler gibt es den Typ des `initializer`, anstelle von `Object`. Im folgenden Beispiel ist die Konstante `naturalLogBase` weist den Typ der Laufzeit `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 Im Beispiel oben wird der <xref:System.Type.ToString%2A> Methode für die <xref:System.Type> zurückgegebenes Objekt der [GetType-Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), da <xref:System.Type> kann nicht konvertiert werden, um `String` mit `CStr`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)
- [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konstanten und Enumerationen](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
