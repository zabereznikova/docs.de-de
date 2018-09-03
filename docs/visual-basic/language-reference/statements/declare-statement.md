---
title: Declare-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 343ee168809fc63ef63559eda0fd018abde684e7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485741"
---
# <a name="declare-statement"></a>Declare Statement
Deklariert einen Verweis auf eine Prozedur in einer externen Datei implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Privat geschützt](../../language-reference/modifiers/private-protected.md)<br /><br /> Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Dies ist optional. Gibt an, Zeichensätze und Informationen zu suchen. Einer der folgenden Werte ist möglich:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (Standard)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur keinen Wert zurückgibt.|  
|`Function`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass es sich bei die externe Prozedur, einen Wert zurückgibt.|  
|`name`|Erforderlich. Der Name der dieser externe Verweis. Weitere Informationen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Erforderlich. Führt eine `Lib` -Klausel, die die externe Datei (DLL- oder Coderessource) identifiziert, die eine externe Prozedur enthält.|  
|`libname`|Erforderlich. Der Name der Datei, die die deklarierte Prozedur enthält.|  
|`Alias`|Dies ist optional. Gibt an, dass die Prozedur deklariert wird in der Datei mit dem Namen im angegebenen identifiziert werden kann `name`. Sie geben ihre Bezeichnung in `aliasname`.|  
|`aliasname`|Erforderlich, wenn Sie die `Alias` Schlüsselwort. Eine Zeichenfolge, die die Prozedur in eine von zwei Arten identifiziert:<br /><br /> Der Name des Einstiegspunkts der Prozedur in der Datei in Anführungszeichen (`""`)<br /><br /> - oder - <br /><br /> Ein Nummernzeichen (`#`) gefolgt von der eine ganze Zahl, die Ordnungszahl der Prozedureinstiegspunkt innerhalb einer Datei|  
|`parameterlist`|Erforderlich, wenn die Prozedur Parameter annimmt. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Erforderlich, wenn `Function` angegeben ist und `Option Strict` ist `On`. Der Datentyp des Werts von der Prozedur zurückgegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Manchmal müssen Sie zum Aufrufen einer Prozedur, die in einer Datei (z. B. eine DLL- oder Coderessource) außerhalb des Projekts definiert. Wenn Sie dies tun, Visual Basic-Compiler keinen Zugriff auf die Informationen, die die Prozedur richtig aufrufen muss, z. B. auf dem sich die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und den Zeichenfolge-Zeichensatz verwendet. Die `Declare` -Anweisung erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Sie können `Declare` nur auf Modulebene verwenden. Dies bedeutet, dass die *Deklarationskontext* für ein externer Verweis eine Klasse, Struktur oder Modul muss, und es nicht, eine Quelldatei, Namespace, Schnittstelle, Prozedur oder Block möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Standardzugriff für externe Verweise [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
## <a name="rules"></a>Regeln  
  
-   **Attribute.** Sie können Attribute auf ein externer Verweis anwenden. Jedes Attribut, die Sie anwenden, wirkt sich nur in Ihrem Projekt, nicht in der externen Datei.  
  
-   **Modifizierer.** Externe Prozeduren sind implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Sie können keine der `Shared` -Schlüsselwort deklarieren ein externer Verweis, und Sie den freigegebenen Status alter kann nicht.  
  
     Eine externe Prozedur kann nicht beim Überschreiben von teilnehmen, Implementieren von Schnittstellenmembern oder Behandeln von Ereignissen. Daher können keine der `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, oder `Handles` -Schlüsselwort in einer `Declare` Anweisung.  
  
-   **Name der externen Prozedur.** Sie müssen keine dieser externen Verweis auf den gleichen Namen geben (in `name`) als der Name der Prozedur Einstiegspunkt in die externe Datei (`aliasname`). Sie können eine `Alias` Klausel, um den Namen des Einstiegspunkts anzugeben. Dies kann nützlich, wenn die externe Prozedur den gleichen Namen wie eine reservierte Visual Basic-Modifizierer oder eine Variable, Prozedur oder eines anderen Programmierelements im gleichen Bereich enthält sein.  
  
    > [!NOTE]
    >  Einstiegspunkt-Namen in die meisten DLLs sind Groß-/Kleinschreibung beachtet.  
  
-   **Anzahl der externen Prozedur.** Alternativ können Sie verwenden eine `Alias` Klausel, um die Ordinalzahl des Einstiegspunkts in der Exporttabelle der externen Datei anzugeben. Beginnen Sie zu diesem Zweck `aliasname` mit einem Nummernzeichen (`#`). Dies kann nützlich sein, wenn alle Zeichen in den externen Prozedurnamen in Visual Basic nicht zulässig ist, oder wenn es sich bei die externe Datei das Verfahren ohne Namen exportiert.  
  
## <a name="data-type-rules"></a>Daten – Typenregeln  
  
-   **Parameterdatentypen.** Wenn `Option Strict` ist `On`, geben Sie den Datentyp jedes Parameters im `parameterlist`. Dies kann einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle sein. In `parameterlist`, Sie verwenden eine `As` -Klausel, um den Datentyp des Arguments an jeden Parameter zu übergebenden angeben.  
  
    > [!NOTE]
    >  Wenn die externe Prozedur nicht für .NET Framework geschrieben wurde, müssen Sie darauf achten, die die Datentypen entsprechen. Angenommen, Sie deklarieren, dass einen externen Verweis auf eine Visual Basic 6.0-Prozedur mit einer `Integer` Parameter (16 Bits in Visual Basic 6.0), müssen Sie das entsprechende Argument als identifizieren `Short` in die `Declare` -Anweisung, da dies die 16 - Bit-Ganzzahl-Typ in Visual Basic. Auf ähnliche Weise `Long` verfügt über eine andere Datenbreite in Visual Basic 6.0 und `Date` wird anders implementiert.  
  
-   **Datentyp zurück.** Wenn die externe Prozedur ist eine `Function` und `Option Strict` ist `On`, geben Sie den Datentyp des Werts an den aufrufenden Code zurückgegeben. Dies kann einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle sein.  
  
    > [!NOTE]
    >  Visual Basic-Compiler überprüft nicht, dass Ihre Datentypen durch die der externen Prozedur kompatibel sind. Wenn ein Konflikt vorliegt, wird die common Language Runtime generiert eine <xref:System.Runtime.InteropServices.MarshalDirectiveException> -Ausnahme zur Laufzeit.  
  
-   **Standarddatentypen.** Wenn `Option Strict` ist `Off` und Sie nicht angeben, dass der Datentyp eines Parameters in `parameterlist`, Visual Basic-Compiler konvertiert das entsprechende Argument in der [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md). Auf ähnliche Weise, wenn Sie keinen angeben `returntype`, nimmt der Compiler den Typ Daten zurückgeben sollen `Object`.  
  
    > [!NOTE]
    >  Da Sie mit einer externen Prozedur arbeiten, die möglicherweise auf einer anderen Plattform geschrieben wurden, ist es gefährlich, Annahmen über Datentypen arbeiten oder die sie auf den Standardwert zuzulassen. Es ist viel sicherer, den Datentyp jedes Parameters und des Rückgabewerts, angeben, sofern vorhanden. Dies verbessert auch die Lesbarkeit des Codes.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Bereich.** Ein externer Verweis ist der Gültigkeitsbereich der Klasse, Struktur oder Moduls.  
  
-   **Lebensdauer.** Ein externer Verweis verfügt über die gleiche Lebensdauer wie die Klasse, Struktur oder Modul, in dem sie deklariert ist.  
  
-   **Aufrufen einer externen Prozedur an.** Sie rufen eine externe Prozedur auf die gleiche Weise, die Sie aufrufen eine `Function` oder `Sub` Prozedur – indem Sie diesen in einem Ausdruck verwenden, wenn es sich um einen Wert zurückgibt, oder durch Angabe in einer [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md) , wenn sie keinen Wert zurückgibt.  
  
     Sie Argumente übergeben, genau wie angegeben, von der externen Prozedur `parameterlist` in die `Declare` Anweisung. Führen Sie nicht berücksichtigen Sie wie die Parameter in der externen Datei ursprünglich deklariert wurden. Auf ähnliche Weise ist ein Wert zurückgegeben, verwenden sie genau wie angegeben durch `returntype` in die `Declare` Anweisung.  
  
-   **Zeichensätze.** Sie können angeben, `charsetmodifier` wie Visual Basic Zeichenfolgen beim Aufruf der externen Prozedur marshallen soll. Die `Ansi` Modifizierer, leitet Visual Basic alle Zeichenfolgen in ANSI-Werte, und die `Unicode` Modifizierer leitet er alle Zeichenfolgen in Unicode-Werte. Die `Auto` Modifizierer leitet Visual Basic zum Marshallen von Zeichenfolgen gemäß der .NET Framework-Regeln basierend auf dem externen Verweis `name`, oder `aliasname` angegeben. Der Standardwert ist `Ansi`.  
  
     `charsetmodifier` gibt auch an, wie Visual Basic die externe Prozedur in ihrer externen Datei aussehen sollte. `Ansi` und `Unicode` weisen Visual Basic, ohne den Namen ändern, während der Suche zu suchen. `Auto` weist Visual Basic den Basiszeichensatz der Laufzeitplattform ermitteln und ändern Sie den Namen der externen Prozedur möglicherweise wie folgt:  
  
    -   Klicken Sie auf eine ANSI-Plattform, z. B. Windows 95, Windows 98 oder Windows Millennium Edition müssen Sie zunächst die externe Prozedur keine Änderung von Gerätenamen gesucht. Wenn dies fehlschlägt, fügen Sie "A" bis zum Ende des Namens der externen Prozedur und die Suche erneut.  
  
    -   Auf einer Unicode-Plattform, z. B. Windows NT, Windows 2000 oder Windows XP müssen Sie zunächst die externe Prozedur keine Änderung von Gerätenamen gesucht. Wenn dies fehlschlägt, hängen Sie "W" am Ende der externen Prozedur benennen und die Suche erneut aus.  
  
-   **Mechanismus.** Visual Basic verwendet das .NET Framework *Plattformaufruf* (PInvoke)-Mechanismus zum Lösen und Zugriff auf externe Prozeduren. Die `Declare` Anweisung und die <xref:System.Runtime.InteropServices.DllImportAttribute> Klasse, die beide automatisch diesen Mechanismus verwenden, und keine Kenntnisse über PInvoke ist nicht erforderlich. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Wenn die externe Prozedur außerhalb der common Language Runtime (CLR) ausgeführt wird, ist es *von nicht verwaltetem Code*. Wenn Sie eine solche Prozedur, z. B. eine Win32-API-Funktion oder einer COM-Methode aufrufen können Sie Ihre Anwendung Sicherheitsrisiken verfügbar machen. Weitere Informationen finden Sie unter [Secure Coding Guidelines für nicht verwalteten Code](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert einen externen Verweis auf eine `Function` Prozedur, die den aktuellen Benutzernamen zurückgibt. Es ruft dann die externe Prozedur `GetUserNameA` als Teil der `getUser` Verfahren.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Runtime.InteropServices.DllImportAttribute> bietet eine alternative Möglichkeit der Verwendung von Funktionen in nicht verwaltetem Code. Das folgende Beispiel deklariert eine importierte Funktion ohne Verwendung einer `Declare` Anweisung.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
