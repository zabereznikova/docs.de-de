---
title: Declare Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2560f34a5130ef7453b50ffb4495b67bf1dfa4c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`attributelist`|Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Dies ist optional. Zeichensätze und gibt Informationen zu suchen. Einer der folgenden Werte ist möglich:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (Standard)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur keinen Wert zurückgibt.|  
|`Function`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur einen Wert zurückgibt.|  
|`name`|Erforderlich. Name des diesen externen Verweis. Weitere Informationen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Erforderlich. Führt eine `Lib` -Klausel, die die externe Datei (DLL oder die Ressource) identifiziert, die eine externe Prozedur enthält.|  
|`libname`|Erforderlich. Der Name der Datei, die die deklarierte Prozedur enthält.|  
|`Alias`|Dies ist optional. Gibt an, dass die Prozedur deklariert wird innerhalb einer Datei mit dem Namen im angegebenen identifiziert werden kann `name`. Geben Sie die Kennung in `aliasname`.|  
|`aliasname`|Erforderlich, wenn Sie mithilfe der `Alias` Schlüsselwort. Eine Zeichenfolge, die die Prozedur in einer von zwei Methoden identifiziert:<br /><br /> Der Name des Einstiegspunkts der Prozedur in ihrer Datei in Anführungszeichen (`""`)<br /><br /> - oder - <br /><br /> Ein Nummernzeichen (`#`) gefolgt von einer Ganzzahl, die die Ordinalzahl der Prozedureinstiegspunkt innerhalb einer Datei angeben|  
|`parameterlist`|Erforderlich, wenn die Prozedur Parameter annimmt. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Erforderlich, wenn `Function` angegeben ist und `Option Strict` ist `On`. Der Datentyp des Werts von der Prozedur zurückgegeben.|  
  
## <a name="remarks"></a>Hinweise  
 In einigen Fällen müssen Sie zum Aufrufen einer Prozedur in einer Datei (z. B. eine DLL oder Code-Ressource) außerhalb des Projekts definiert. Wenn Sie dies tun, Visual Basic-Compiler keinen Zugriff auf die Informationen zum ordnungsgemäßen Aufrufen der Prozedur erforderlich, z. B. auf dem sich die Prozedur befindet, wie festgestellt wird, die Aufrufsequenz und Rückgabetyp und den String-Zeichensatz verwendet. Die `Declare` -Anweisung erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Sie können `Declare` nur auf Modulebene verwenden. Dies bedeutet, dass die *Deklarationskontext* für ein externer Verweis muss eine Klasse, Struktur oder Modul, und nicht mit einer Quelldatei, Namespace, Schnittstelle, Prozedur oder Block. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Standardzugriff für externe Verweise [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
## <a name="rules"></a>Regeln  
  
-   **Attribute.** Sie können Attribute auf ein externer Verweis anwenden. Jedes Attribut, die Sie vornehmen, wirkt sich nur in Ihrem Projekt, nicht in der externen Datei.  
  
-   **Modifizierer.** Externe Prozeduren sind implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Sie können keine der `Shared` -Schlüsselwort, wenn ein externer Verweis, und Sie deklarieren den freigegebenen Status nicht ändern können.  
  
     Eine externe Prozedur kann nicht überschreiben teilnehmen, Implementieren von Schnittstellenmembern oder Ereignisse zu behandeln. Entsprechend können Sie keine der `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, oder `Handles` -Schlüsselwort in einer `Declare` Anweisung.  
  
-   **Name der externen Prozedur.** Sie müssen keine diesen externen Verweis auf den gleichen Namen geben (in `name`) als der Name der Prozedur Einstiegspunkt in die externe Datei (`aliasname`). Sie können eine `Alias` -Klausel, um den Einstiegspunkt Namen angeben. Dies kann sinnvoll, wenn die externe Prozedur den gleichen Namen wie eine reservierte Visual Basic-Modifizierer oder eine Variable, Prozedur oder eines anderen Programmierelements im selben Bereich haben.  
  
    > [!NOTE]
    >  Einstiegspunktfunktion mit dem Namen in den meisten DLLs sind Groß-/Kleinschreibung beachtet.  
  
-   **Externe Prozedurnummer.** Alternativ können Sie eine `Alias` -Klausel, um die Ordinalzahl des Einstiegspunkts in der Exporttabelle der externen Datei anzugeben. Dazu starten Sie `aliasname` mit einem Nummernzeichen (`#`). Dies kann nützlich sein, wenn alle Zeichen im Namen externen Prozedur in Visual Basic nicht zulässig ist, oder wenn die Prozedur ohne Namen können die externe Datei exportieren.  
  
## <a name="data-type-rules"></a>Regeln für die Art von Daten  
  
-   **Parameterdatentypen.** Wenn `Option Strict` ist `On`, geben Sie den Datentyp jedes Parameters im `parameterlist`. Dies kann einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle sein. In `parameterlist`, Sie verwenden eine `As` -Klausel, um den Datentyp des Arguments an jeden Parameter zu übergebenden angeben.  
  
    > [!NOTE]
    >  Wenn die externe Prozedur nicht für .NET Framework geschrieben wurde, Sie müssen darauf achten, die die Datentypen entsprechen. Angenommen, Sie deklarieren, dass einen externen Verweis auf eine Visual Basic 6.0-Prozedur mit einer `Integer` Parameter (16 Bits in Visual Basic 6.0), müssen Sie das entsprechende Argument als identifizieren `Short` in der `Declare` -Anweisung, da dies die 16 - in Visual Basic-Bit-Ganzzahl-Typ. Auf ähnliche Weise `Long` verfügt über eine andere Datenbreite in Visual Basic 6.0, und `Date` wird anders implementiert.  
  
-   **Datentyp zurück.** Wenn die externe Prozedur ist eine `Function` und `Option Strict` ist `On`, geben Sie den Datentyp des Werts an den aufrufenden Code zurückgegeben. Dies kann einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle sein.  
  
    > [!NOTE]
    >  Visual Basic-Compiler überprüft nicht, dass Ihre Datentypen mit denen die externe Prozedur kompatibel sind. Wenn es ein Konflikt besteht, die common Language Runtime generiert eine <xref:System.Runtime.InteropServices.MarshalDirectiveException> -Ausnahme zur Laufzeit.  
  
-   **Standarddatentypen.** Wenn `Option Strict` ist `Off` und Sie keinen angeben, dass der Datentyp eines Parameters in `parameterlist`, Visual Basic-Compiler konvertiert das entsprechende Argument in der [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md). Auf ähnliche Weise, wenn Sie keinen angeben `returntype`, nimmt der Compiler den Datentyp des Rückgabewerts zu `Object`.  
  
    > [!NOTE]
    >  Da Sie mit einer externen Prozedur arbeiten, die auf einer anderen Plattform geschrieben wurden, ist es gefährlich, damit keine Annahmen über Datentypen oder auf den Standardwert zu können. Es ist wesentlich sicherer, den Datentyp jedes Parameters und des Rückgabewerts, angeben, sofern vorhanden. Dies wird auch verbessert die Lesbarkeit des Codes.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Bereich.** Ein externer Verweis ist der Gültigkeitsbereich der Klasse, Struktur oder Modul.  
  
-   **Lebensdauer.** Ein externer Verweis verfügt über dieselbe Lebensdauer wie die Klasse, Struktur oder Modul, in dem sie deklariert ist.  
  
-   **Aufrufen einer externen Prozedur an.** Sie rufen eine externe Prozedur auf die gleiche Weise, die Sie Aufrufen einer `Function` oder `Sub` Prozedur – indem Sie diesen in einem Ausdruck verwenden, wenn es sich um einen Wert zurückgibt, oder durch Angabe in einen [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md) , wenn sie keinen Wert zurückgibt.  
  
     Übergeben Sie Argumente an die externe Prozedur genau entsprechend den Angaben von `parameterlist` in der `Declare` Anweisung. Führen Sie nicht berücksichtigen Sie wie die Parameter in der externen Datei ursprünglich deklariert wurden. Ebenso ist ein Wert zurückgegeben, verwenden sie genau entsprechend den Angaben von `returntype` in der `Declare` Anweisung.  
  
-   **Zeichensätze.** Sie können angeben, `charsetmodifier` wie Visual Basic Zeichenfolgen marshallen soll, wenn sie die externe Prozedur aufruft. Die `Ansi` Modifizierer marshallt Visual Basic alle Zeichenfolgen in ANSI-Werte und die `Unicode` Modifizierer leitet er alle Zeichenfolgen in Unicode-Werte. Die `Auto` Modifizierer leitet Visual Basic zum Marshallen von Zeichenfolgen gemäß der .NET Framework-Regeln basierend auf der externen Verweis `name`, oder `aliasname` angegeben. Der Standardwert ist `Ansi`.  
  
     `charsetmodifier`gibt auch an, wie Visual Basic die externe Prozedur innerhalb einer externen Datei aussehen soll. `Ansi`und `Unicode` weisen Visual Basic, die ohne den Namen ändern, während der Suche gesucht. `Auto`weist Visual Basic Basiszeichensatz der Plattform zur Laufzeit bestimmen und ändern Sie den Namen der externen Prozedur, möglicherweise wie folgt:  
  
    -   Auf einer ANSI-Plattform, z. B. Windows 95, Windows 98 oder Windows Millennium Edition müssen Sie zunächst die externe Prozedur ohne Namensänderung gesucht. Schlägt dies fehl, fügen Sie an "A" bis zum Ende der externen Prozedurnamen und suchen Sie erneut.  
  
    -   Auf einer Unicode-Plattform, z. B. Windows NT, Windows 2000 oder Windows XP müssen Sie zunächst die externe Prozedur ohne Namensänderung gesucht. Wenn dies fehlschlägt, hängen Sie "W" bis zum Ende der externe Prozedur benennen, und suchen Sie erneut.  
  
-   **Mechanismus.** Visual Basic verwendet .NET Framework *Plattformaufruf* (PInvoke)-Mechanismus zum Auflösen und externe Prozeduren zugreifen. Die `Declare` Anweisung und die <xref:System.Runtime.InteropServices.DllImportAttribute> Klasse sowohl automatisch diesen Mechanismus verwenden, und Sie benötigen keine Kenntnis von PInvoke. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Wenn die externe Prozedur außerhalb der common Language Runtime (CLR) ausgeführt wird, ist es *nicht verwaltetem Code*. Wenn Sie eine solche Prozedur, z. B. eine Win32-API-Funktion oder eine COM-Methode aufrufen können Sie Ihre Anwendung Sicherheitsrisiken verfügbar machen. Weitere Informationen finden Sie unter [Codierungsrichtlinien für nicht verwalteten Code Secure](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert einen externen Verweis auf eine `Function` Prozedur, die den aktuellen Benutzernamen zurückgibt. Er ruft dann die externe Prozedur `GetUserNameA` als Teil der `getUser` Prozedur.  
  
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
