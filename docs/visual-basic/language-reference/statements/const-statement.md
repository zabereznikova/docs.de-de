---
title: Const-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: a5842e284eaa858e7a66160060123edc21858a3a
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233846"
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
 Dies ist optional. Verwenden Sie diese Option, um anzugeben, welcher Code auf diese Konstanten zugreifen kann. Kann [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../visual-basic/language-reference/modifiers/protected.md), ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), oder [Privaten, geschützten](../../language-reference/modifiers/private-protected.md).
  
 `Shadows`  
 Dies ist optional. Hiermit können Sie deklarieren und ein Programmierelement in einer Basisklasse auszublenden. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Erforderlich. Liste der Konstanten, die in dieser Anweisung deklariert wird.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Jede `constant` weist folgende Syntax und Bestandteile auf:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`constantname`|Erforderlich. Die Namen der Konstanten. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp der Konstante.|  
|`initializer`|Erforderlich. Ausdruck, der zur Kompilierzeit ausgewertet und die Konstante zugewiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen Wert, der nie ändert, in der Anwendung haben, können Sie definieren eine benannte Konstante und verwenden sie statt eines Literalwerts. Ein Name ist leichter zu merken als ein Wert. Sie können die Konstante nur einmal definieren und an vielen Stellen im Code verwenden. Wenn in einer höheren Version Sie den Wert neu definieren müssen die `Const` -Anweisung ist der einzige Ort, Sie eine Änderung vornehmen müssen.  
  
 Sie können `Const` nur auf Modul- oder Prozedur. Dies bedeutet, dass die *Deklarationskontext* für eine Variable muss eine Klasse, Struktur, Modul, Prozedur oder blockieren, und nicht mit einer Quelldatei, Namespace oder Schnittstelle. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Lokale Konstanten (innerhalb einer Prozedur)-Standard, um öffentlichen Zugriff, und Sie können keine keine Zugriffsmodifizierer darauf. Standardmäßig gilt für Klassen- und Konstanten (außerhalb einer Prozedur) privaten Zugriff und Struktur Member Konstanten standardmäßig öffentlichen Zugriff auf. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Eine Konstante deklariert auf Modulebene außerhalb einer Prozedur wird eine *Memberkonstante*; es ist ein Member der Klasse, Struktur oder Modul deklariert, die ihn.  
  
     Eine Konstante deklariert auf Prozedurebene ist ein *lokale Konstante*; es lokal auf dem Prozedur oder ein Block, der sie deklariert ist.  
  
-   **Attribute.** Sie können Attribute nur für Memberkonstanten und nicht auf lokale Konstanten anwenden. Ein Attribut trägt dazu bei Informationen zu den Metadaten der Assembly, für die temporäre Speicherung, z. B. lokale Konstanten sinnvoll ist.  
  
-   **Modifizierer.** Standardmäßig sind alle Konstanten `Shared`, `Static`, und `ReadOnly`. Sämtliche dieser Schlüsselwörter können keine beim Deklarieren einer Konstante.  
  
     Auf Prozedurebene, können keine `Shadows` Zugriffsmodifizierern Lokale Konstanten deklarieren.  
  
-   **Mehrere Konstanten.** Sie können mehrere Konstanten in der gleichen deklarationsanweisung deklarieren angeben der `constantname` für jeden Teil. Mehrere Konstanten werden durch Kommas getrennt.  
  
## <a name="data-type-rules"></a>Regeln für die Art von Daten  
  
-   **Datentypen.** Die `Const` -Anweisung kann den Datentyp einer Variablen deklarieren. Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration angeben.  
  
-   **Der Standardtyp.** Wenn Sie keinen angeben `datatype`, die Konstante hat den Datentyp der `initializer`. Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` konvertierbar sein muss `datatype`. Wenn weder `datatype` noch `initializer` vorhanden ist, der Datentyp der Standardwert ist `Object`.  
  
-   **Andere Typen.** Sie können für unterschiedliche Konstanten unterschiedliche Datentypen angeben, indem Sie eine separate `As` -Klausel für jede Variable, die Sie deklarieren. Allerdings kann nicht mehrere Konstanten desselben Typs werden mit einer gemeinsamen deklariert `As` Klausel.  
  
-   **die Initialisierung.** Sie müssen den Wert jeder Konstante in initialisieren `constantlist`. Verwenden Sie `initializer` , geben Sie einen Ausdruck, der Konstante zugewiesen werden soll. Der Ausdruck kann eine beliebige Kombination von Literalen, anderen, die bereits definierte, Konstanten und Enumerationsmembern, die bereits definiert sind. Sie können arithmetische und logische Operatoren verwenden, solche Elemente kombinieren.  
  
     Sie können keine Variablen oder Funktionen in `initializer`. Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`. Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` Argument, da, die zur Kompilierzeit ausgewertet werden kann.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Bereich.** Lokale Konstanten werden nur innerhalb ihrer Prozedur oder eines Blocks zugegriffen werden. Memberkonstanten sind kann an einer beliebigen Stelle innerhalb ihrer Klasse, Struktur oder Modul zugegriffen werden.  
  
-   **Qualifizierung.** Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss eine Memberkonstante Name durch den Namen der Klasse, der Struktur oder des Moduls qualifizieren. Code außerhalb einer Prozedur oder eines Blocks kann auf keine lokalen Konstanten innerhalb dieser Prozedur oder eines Blocks verweisen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Const` -Anweisung zum Deklarieren von Konstanten für die Verwendung anstelle von literalen Werten.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Wenn Sie eine Konstante mit dem Datentyp definieren `Object`, Visual Basic-Compiler gibt den Typ des `initializer`, anstelle von `Object`. Im folgenden Beispiel wird die Konstante `naturalLogBase` hat den Laufzeittyp `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 Im vorherige Beispiel wird die <xref:System.Type.ToString%2A> Methode für die <xref:System.Type> zurückgegebenes Objekt der [Operators "GetType"](../../../visual-basic/language-reference/operators/gettype-operator.md), da <xref:System.Type> kann nicht konvertiert werden, um `String` mit `CStr`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Konstanten und Enumerationen](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
