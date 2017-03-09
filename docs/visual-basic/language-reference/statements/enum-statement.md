---
title: "Enum-Anweisung (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Enum"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Enumerationskonstanten"
  - "Enum-Anweisung"
  - "Private-Schlüsselwort, Enum-Anweisungen"
  - "Public-Schlüsselwort in Enum-Anweisung"
  - "Variablen [Visual Basic], enumeration"
  - "Konstanten, aufgezählt"
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 44
---
# Enum-Anweisung (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Deklariert eine Enumeration und definiert die Werte ihrer Member.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a>Teile  
  
-   `attributelist`  
  
     Optional. Liste der Attribute, die auf diese Enumeration anwenden. Sie setzen die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").  
  
     Die <xref:System.FlagsAttribute> Attribut gibt an, dass der Wert einer Instanz der Enumeration kann mehrere Enumerationsmember und jedes Element ein Bitfeld im Enumerationswert darstellt.  
  
-   `accessmodifier`  
  
     Optional. Gibt an, welcher Code auf diese Enumeration zugreifen kann. Einer der folgenden Werte ist möglich:  
  
    -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Geschützte](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
     Sie können angeben, `Protected``Friend` um Zugriff von Code innerhalb der Enumeration-Klasse, einer abgeleiteten Klasse oder der gleichen Assembly zuzulassen.  
  
-   `Shadows`  
  
     Optional. Gibt an, dass diese Enumeration erneut deklariert und ein Programmierelement mit derselben Bezeichnung oder eine Gruppe überladener Elemente in einer Basisklasse ausgeblendet. Sie können angeben, [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md) nur für die Enumeration selbst, nicht für einen Member.  
  
-   `enumerationname`  
  
     Erforderlich. Der Name der Enumeration. Informationen zu gültigen Namen finden Sie unter [Elementnamen deklariert](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `datatype`  
  
     Optional. Der Datentyp der Enumeration und allen zugehörigen Membern.  
  
-   `memberlist`  
  
     Erforderlich. Liste der Memberkonstanten, die in dieser Anweisung deklariert werden. Auf einzelnen Quellcodezeilen werden mehrere Member aufgeführt.  
  
     Jede `member` hat die folgende Syntax und Bestandteile: `[<attribute list>] member name [ = initializer ]`  
  
    |||  
    |-|-|  
    |Segment|Beschreibung|  
    |`membername`|Erforderlich. Der Name dieses Members.|  
    |`initializer`|Optional. Ein Ausdruck, der zur Kompilierzeit ausgewertet und diesem Member zugewiesen.|  
  
-   `End` `Enum`  
  
     Beendet den `Enum`-Block.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine Gruppe unveränderlicher Werte, die logisch miteinander verknüpft sind haben, können Sie diese zusammen in einer Enumeration definieren. Dadurch werden aussagekräftige Namen für die Enumeration und seine Member, die leichter merken als die Werte sind. Sie können dann die Enumerationsmember an vielen Stellen in Ihrem Code verwenden.  
  
 Die Vorteile der Verwendung von Enumerationen sind unter anderem:  
  
-   Fehler aufgrund eines vertauschen oder falsch eingegebene Zahlen wird reduziert.  
  
-   Erleichtert die Werte in der Zukunft ändern.  
  
-   Ist der Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.  
  
-   Sicherstellung der Vorwärtskompatibilität. Wenn Sie Enumerationen verwenden, ist der Code weniger wahrscheinlich fehlschlägt, wenn jemand die Namen der entsprechenden Werte ändert.  
  
 Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und eine Menge von Elementen. Jedes Element stellt eine Konstante dar.  
  
 Eine Enumeration, die auf die Klasse, Struktur, Modul oder Schnittstellenebene außerhalb einer Prozedur deklariert ist ein *Element Enumeration*. Es ist ein Mitglied der Klasse, Struktur, Modul oder Schnittstelle, die es deklariert.  
  
 Enumerationen für Namespacemember können von überall in ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden. Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss ein der Memberenumeration den Namen mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren. Sie können vermeiden, dass durch Hinzufügen von vollqualifizierte Namen verwenden eine [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Anweisung in der Quelldatei.  
  
 Eine Enumeration, die auf Namespaceebene außerhalb jeder Klasse, Struktur, Modul oder Schnittstelle deklariert ist, ein Mitglied der Namespace, in dem es angezeigt wird.  
  
 Die *Deklarationskontext* für eine Enumeration eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle sein muss und keine Prozedur sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Sie können Attribute auf die Enumeration als Ganzes, jedoch nicht auf ihre Member einzeln anwenden. Ein Attribut fügt die Informationen in den Metadaten der Assembly.  
  
## <a name="data-type"></a>Datentyp  
 Die `Enum` -Anweisung kann den Datentyp einer Enumeration deklarieren. Jedes Element hat den Enumerationstyp Daten. Sie können angeben, `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort`.  
  
 Wenn Sie keinen angeben `datatype` für die Enumeration übernimmt jeder Member den Datentyp der `initializer`. Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` muss in konvertierbar sein `datatype`. Wenn weder `datatype` noch `initializer` vorhanden ist, der Datentyp, der Standardwert ist `Integer`.  
  
## <a name="initializing-members"></a>Initialisieren von Membern  
 Die `Enum` -Anweisung kann den Inhalt der ausgewählten Elemente in initialisieren `memberlist`. Verwenden Sie `initializer` geben Sie einen Ausdruck, der das Element zugewiesen werden soll.  
  
 Wenn Sie keinen angeben `initializer` für ein Mitglied initialisiert Visual Basic diesen entweder 0 (null) (ist dies die erste `member` in `memberlist`), oder auf einen Wert, der um eins größer als die des unmittelbar vorangehenden `member`.  
  
 In jedem bereitgestellten Ausdruck `initializer` kann eine beliebige Kombination von Literalen, andere, bereits definierte, Konstanten und Enumerationsmember, der bereits definiert sind, einschließlich eines vorherigen Members dieser Enumeration. Sie können arithmetische und logische Operatoren verwenden, zur Kombination dieser Elemente.  
  
 Sie können keine Variablen oder Funktionen in `initializer`. Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`. Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` -Argument, das zum Zeitpunkt der Kompilierung ausgewertet werden können.  
  
 Enumerationen können keine Gleitkommawerte haben. Wenn ein Element einen Gleitkommawert zugewiesen ist und `Option Strict` auf on festgelegt ist, tritt ein Compilerfehler auf. Wenn `Option Strict` deaktiviert ist, wird automatisch konvertierte Wert der `Enum` Typ.  
  
 Wenn der Wert eines Members den für den zugrunde liegenden Datentyp zulässigen Bereich überschreitet oder Member, die von den zugrunde liegenden Datentyp zulässigen Höchstwert initialisiert, meldet der Compiler einen Fehler.  
  
## <a name="modifiers"></a>Modifizierer  
 Klasse, Struktur, Modul und Schnittstellenmember Enumerationen standardmäßig öffentlichen Zugriff auf. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Namespace Member Enumerationen standardmäßig Friend-Zugriff. Sie können ihre Zugriffsebenen auf öffentlich, jedoch nicht auf private oder geschützte anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Alle Enumerationsmember haben Public-Zugriff und können keine Zugriffsmodifizierer auf diesen. Wenn die Enumeration selbst eine restriktivere Zugriffsebene verfügt, hat die Zugriffsebene für die angegebene Enumeration jedoch Vorrang vor.  
  
 Standardmäßig sind alle Enumerationen Typen und ihre Felder sind Konstanten. Aus diesem Grund die `Shared`, `Static`, und `ReadOnly` Schlüsselwörter können nicht verwendet werden, bei der Deklaration einer Enumeration oder ihrer Member.  
  
## <a name="assigning-multiple-values"></a>Zuweisen mehrerer Werte  
 Enumerationen werden in der Regel sich gegenseitig ausschließende Werte darstellen. Durch Einschließen der <xref:System.FlagsAttribute> Attribut in die `Enum` Deklaration können Sie stattdessen Zuweisen mehrerer Werte eine Instanz der Enumeration. Die <xref:System.FlagsAttribute> Attribut gibt an, dass die Enumeration als Bitfeld, d. h. als Gruppe von Flags behandelt werden. Diese heißen *bitweise* Enumerationen.  
  
 Beim Deklarieren einer Enumeration mit den <xref:System.FlagsAttribute> -Attribut, wird empfohlen, für die Werte Potenzen von 2, die ist, 1, 2, 4, 8, 16 und usw. verwenden. Außerdem wird empfohlen, dass "None" der Name eines Elements, dessen Wert 0 ist. Weitere Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `Enum` Anweisung. Hinweis, der das Element so genannte `EggSizeEnum.Medium`, und nicht als `Medium`.  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#41)]  
  
## <a name="example"></a>Beispiel  
 Die Methode im folgenden Beispiel befindet sich außerhalb der `Egg` Klasse. Aus diesem Grund `EggSizeEnum` vollqualifiziert als `Egg.EggSizeEnum`.  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#42)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Enum` Anweisung, um eine Gruppe von verwandten definieren benannte Konstanten. In diesem Fall sind die Werte Farben, die Sie zum Entwerfen von Dateneingabeformularen für eine Datenbank.  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#30)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Werte, die positive und negative Zahlen enthalten.  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#31)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ein `As` -Klausel zur Angabe der `datatype` einer Enumeration.  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#6)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine bitweise Enumeration verwendet. Eine Instanz einer Enumeration bitweise können mehrere Werte zugewiesen werden. Die `Enum` Deklaration enthält die <xref:System.FlagsAttribute> Attribut, das angibt, dass die Enumeration als Satz von Flags behandelt werden kann.  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#61)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Enumeration durchlaufen. Er verwendet die <xref:System.Enum.GetNames%2A> Methode, um ein Array von Elementnamen aus der-Enumeration abzurufen und <xref:System.Enum.GetValues%2A> zum Abrufen eines Arrays der Werte.  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class1.vb#51)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Enum>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)