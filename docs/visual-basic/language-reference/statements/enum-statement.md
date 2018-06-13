---
title: Enum-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 7cac4d5bde9ec617a1877a0605dc6dbab67ddf7f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234015"
---
# <a name="enum-statement-visual-basic"></a>Enum-Anweisung (Visual Basic)
Deklariert eine Enumeration und die Werte der Member definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a>Teile  
  
-   `attributelist`  
  
     Dies ist optional. Liste der Attribute, die für diese Enumeration gelten. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").  
  
     Die <xref:System.FlagsAttribute> Attribut gibt an, dass der Wert einer Instanz der Enumeration mehrere Enumerationsmember enthalten kann und dass jedes Element ein Bitfeld in die Enumerationswert darstellt.  
  
-   `accessmodifier`  
  
     Dies ist optional. Gibt an, welcher Code auf diese Enumeration zugreifen kann. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Geschützt privat](../../language-reference/modifiers/private-protected.md)

-   `Shadows`  
  
     Dies ist optional. Gibt an, dass diese Enumeration erneut deklariert und ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einer Basisklasse ausgeblendet. Sie können angeben, [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md) nur auf die Enumeration selbst sein, nicht auf eines ihrer Elemente.  
  
-   `enumerationname`  
  
     Erforderlich. Der Name der Enumeration. Informationen zu gültigen Namen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `datatype`  
  
     Dies ist optional. Der Datentyp der Enumeration und allen zugehörigen Membern.  
  
-   `memberlist`  
  
     Erforderlich. Liste der Memberkonstanten, die in dieser Anweisung deklariert wird. Mehrere Elemente, die auf einzelne Quellcodezeilen angezeigt werden.  
  
     Jede `member` hat die folgende Syntax und Bestandteile: `[<attribute list>] member name [ = initializer ]`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`membername`|Erforderlich. Der Name dieses Elements.|  
    |`initializer`|Dies ist optional. Ausdruck, der zur Kompilierzeit ausgewertet und bei diesem Member zugewiesen wird.|  
  
-   `End` `Enum`  
  
     Beendet den `Enum`-Block.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen Satz von unveränderlicher Werte, die logisch miteinander verknüpft sind verfügen, können Sie diese zusammen in einer Enumeration definieren. Dies bietet aussagekräftige Namen für die Enumeration und ihre Member, die leichter zu merken als ihre Werte sind. Sie können dann Enumerationsmember an vielen Stellen im Code verwenden.  
  
 Die Vorteile der Verwendung von Enumerationen umfassen Folgendes:  
  
-   Fehler durch Transponieren oder falsch eingegebene Zahlen wird reduziert.  
  
-   Vereinfacht die Werte in der Zukunft ändern.  
  
-   Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.  
  
-   Stellt Aufwärtskompatibilität sicher. Bei Verwendung von Enumerationen ist der Code weniger wahrscheinlich, dass Sie einen Fehler, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.  
  
 Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und eine Menge von Elementen. Jedes Element stellt eine Konstante dar.  
  
 Eine Enumeration, die auf die Klasse, Struktur, Modul oder Schnittstellenebene außerhalb einer Prozedur deklariert ist ein *Memberenumeration*. Es ist ein Mitglied der Klasse, Struktur, Modul oder Schnittstelle, die es deklariert.  
  
 Memberenumerationen können von überall innerhalb ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden. Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss ein der Memberenumeration den Namen mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren. Sie können vermeiden, dass durch Hinzufügen von vollqualifizierte Namen verwenden ein [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Anweisung zur Quelldatei.  
  
 Eine Enumeration, die auf Namespaceebene außerhalb einer Klasse, Struktur, Modul oder Schnittstelle deklariert ist, ein Mitglied der Namespace, in dem er angezeigt wird.  
  
 Die *Deklarationskontext* für eine Enumeration muss eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle, und nicht mit einer Prozedur. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Sie können Attribute auf eine Enumeration als Ganzes, aber nicht auf ihre Member einzeln anwenden. Ein Attribut trägt dazu bei Informationen zu den Metadaten der Assembly.  
  
## <a name="data-type"></a>Datentyp  
 Die `Enum` -Anweisung kann den Datentyp einer Enumeration deklarieren. Jedes Element hat den Enumerationsdatentyp. Sie können angeben, `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort`.  
  
 Wenn Sie keinen angeben `datatype` für die Enumeration jedes Element hat den Datentyp des seine `initializer`. Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` konvertierbar sein muss `datatype`. Wenn weder `datatype` noch `initializer` vorhanden ist, der Datentyp der Standardwert ist `Integer`.  
  
## <a name="initializing-members"></a>Initialisieren von Membern  
 Die `Enum` -Anweisung kann den Inhalt der ausgewählten Elemente in initialisieren `memberlist`. Verwenden Sie `initializer` , geben Sie einen Ausdruck, der das Element zugewiesen werden soll.  
  
 Wenn Sie keinen angeben `initializer` für einen Member, Visual Basic initialisiert es entweder 0 (null) (wird jedoch die erste `member` in `memberlist`), oder auf einen Wert, der um eins größer als die des unmittelbar vorangehenden `member`.  
  
 Der Ausdruck, der in jedem angegebenen `initializer` kann eine beliebige Kombination von Literalen, anderen, bereits definierte, Konstanten und Enumerationsmembern, die bereits definiert sind, einschließlich eines vorherigen Members dieser Enumeration. Sie können arithmetische und logische Operatoren verwenden, solche Elemente kombinieren.  
  
 Sie können keine Variablen oder Funktionen in `initializer`. Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`. Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` Argument, da, die zur Kompilierzeit ausgewertet werden kann.  
  
 Enumerationen können keine Gleitkommawerte haben. Wenn ein Element ein Gleitkommawerts zugewiesen ist und `Option Strict` für auf festgelegt ist, tritt ein Compilerfehler auf. Wenn `Option Strict` deaktiviert ist, wird automatisch konvertierte Wert der `Enum` Typ.  
  
 Wenn der Wert eines Members des zulässigen Bereichs für den zugrunde liegenden Datentyp überschreitet, oder wenn Sie Member mit dem vom zugrunde liegenden Datentyp zulässigen Höchstwert initialisieren, meldet der Compiler einen Fehler aus.  
  
## <a name="modifiers"></a>Modifizierer  
 Klasse, Struktur, Modul und Schnittstellenmember Enumerationen standardmäßig öffentlichen Zugriff auf. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Namespace Member Enumerationen standardmäßig Friend-Zugriff. Sie können ihre Zugriffsebenen öffentlich, jedoch nicht auf private oder geschützte anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Alle Enumerationsmember verfügen über öffentlichen Zugriff und können keine Zugriffsmodifizierer auf diesen. Wenn die Enumeration selbst eine restriktivere Zugriffsebene verfügt, hat die Zugriffsebene für die angegebene Enumeration jedoch Vorrang vor.  
  
 Standardmäßig sind alle Enumerationen Typen und ihre Felder sind Konstanten. Aus diesem Grund die `Shared`, `Static`, und `ReadOnly` Schlüsselwörter nicht verwendet werden, wenn Sie eine Enumeration oder der entsprechenden Member deklarieren.  
  
## <a name="assigning-multiple-values"></a>Zuweisen von mehreren Werten  
 Enumerationen werden in der Regel sich gegenseitig ausschließende Werte darstellen. Durch Einschließen der <xref:System.FlagsAttribute> Attribut in der `Enum` Deklaration enthalten sein, Sie können stattdessen weisen mehrere Werte mit einer Instanz der Enumeration. Die <xref:System.FlagsAttribute> Attribut gibt an, dass die Enumeration als Bitfeld, d. h. als Gruppe von Flags behandelt werden. Diese heißen *bitweise* Enumerationen.  
  
 Wenn Sie eine Enumeration deklarieren, indem die <xref:System.FlagsAttribute> -Attribut, wir empfehlen die Verwendung Potenzen von 2, die ist, 1, 2, 4, 8, 16 usw., für die Werte. Wir empfehlen außerdem, dass "None" der Name eines Elements, dessen Wert 0 ist. Zusätzliche Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `Enum` Anweisung. Beachten Sie, die das Element so genannte `EggSizeEnum.Medium`, und nicht als `Medium`.  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Die Methode im folgenden Beispiel wird außerhalb der `Egg` Klasse. Aus diesem Grund `EggSizeEnum` ist vollqualifizierte als `Egg.EggSizeEnum`.  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Enum` Anweisung zum Definieren eines Gruppe verwandten benannte Konstanten. In diesem Fall sind die Werte, Farben, die Sie auswählen können, um Dateneingabeformulare für eine Datenbank entwerfen.  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Werte, die positive und negative Zahlen enthalten.  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ein `As` -Klausel zur Angabe der `datatype` einer Enumeration.  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie eine bitweise Enumeration verwendet wird. Eine Instanz eine bitweise Enumeration können mehrere Werte zugewiesen werden. Die `Enum` Deklaration enthält die <xref:System.FlagsAttribute> -Attribut, das zeigt an, dass die Enumeration als eine Gruppe von Flags, behandelt werden kann.  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel durchläuft eine Enumeration ab. Er verwendet die <xref:System.Enum.GetNames%2A> Methode, um ein Array von Elementnamen aus der Enumeration abzurufen und <xref:System.Enum.GetValues%2A> zum Abrufen eines Arrays von Elementwerten.  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)
