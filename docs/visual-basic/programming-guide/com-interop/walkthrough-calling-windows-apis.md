---
title: 'Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 34bfb732e2d99b259811573a427ae66628c7fc3a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Exemplarische Vorgehensweise: Aufrufen von Windows-APIs (Visual Basic)
Windows-APIs sind Dynamic Link Libraries (DLLs), die Teil des Windows-Betriebssystems sind. Sie verwenden, um Aufgaben durchzuführen, wenn es schwierig zu entsprechende Verfahren Ihrer Wahl zu schreiben. Windows stellt z. B. eine Funktion namens `FlashWindowEx` , mit der Sie die Titelleiste für eine Anwendung wechseln Sie zwischen dem hellen und dunklen Schatten vornehmen.  
  
 Der Vorteil der Verwendung von Windows-APIs in Ihrem Code ist, dass sie Entwicklungszeit speichern können, da sie Dutzende von nützlichen Funktionen, die bereits geschrieben werden, die darauf warten, zu verwendende enthalten. Der Nachteil ist, dass die Windows-APIs arbeiten mit und fehleranfällig, wenn etwas schief geht schwierig sein kann.  
  
 Windows-APIs stellen eine besondere Kategorie der Interoperabilität dar. Windows-APIs verwenden nicht verwalteten Code, verfügen nicht über integrierte Typbibliotheken und verwenden die Datentypen unterscheiden, die mit Visual Studio verwendet. Aufgrund dieser Unterschiede und da Windows-APIs keine COM-Objekten, die Interoperabilität mit Windows-APIs sind und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] erfolgt mithilfe der Plattform aufrufen, oder PInvoke. Plattformaufruf ist ein Dienst, verwaltetem Code zum Aufrufen von nicht verwalteten Funktionen in DLLs implementiert werden können. Weitere Informationen finden Sie unter [nicht verwaltete DLL-Funktionen nutzen](../../../framework/interop/consuming-unmanaged-dll-functions.md). Sie können PInvoke in Visual Basic verwenden, indem Sie entweder die `Declare` -Anweisung oder durch Anwenden der `DllImport` -Attribut auf eine leere Prozedur.  
  
 Windows-API-Aufrufe werden selten mit Visual Basic .NET jedoch ein wichtiger Teil der Visual Basic-Programmierung in der Vergangenheit wurden. Wann immer möglich, sollten Sie verwalteten Code aus verwenden die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Aufgaben anstelle von Windows-API-Aufrufe. Diese exemplarische Vorgehensweise enthält Informationen für die Situationen, in denen die Verwendung Windows-APIs erforderlich ist.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Deklarieren von API-Aufrufe mit  
 Die gängigste Methode zum Aufrufen von Windows-APIs wird mithilfe der `Declare` Anweisung.  
  
#### <a name="to-declare-a-dll-procedure"></a>Deklarieren eine DLL-Prozedur  
  
1.  Bestimmen Sie den Namen, der die Funktion, die Sie aufrufen möchten, und seine Argumente, Argumenttypen und -Wert, als auch den Namen und Speicherort der DLL, die darin enthaltenen zurück.  
  
    > [!NOTE]
    >  Vollständige Informationen zu den Windows-APIs finden Sie unter der Win32 SDK-Dokumentation in der Platform SDK-Windows-API. Weitere Informationen zu den Konstanten, die Windows-APIs verwenden, überprüfen Sie die Headerdateien, z. B. Windows.h im Plattform-SDK enthalten.  
  
2.  Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie auf **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Wählen Sie **Windows-Anwendung** aus der Liste der Projektvorlagen für Visual Basic. Das neue Projekt wird angezeigt.  
  
4.  Fügen Sie die folgenden `Declare` Funktion entweder an die Klasse oder das Modul, in dem Sie die DLL verwenden möchten:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Bestandteile der Declare-Anweisung  
 Die `Declare` -Anweisung enthält die folgenden Elemente.  
  
#### <a name="auto-modifier"></a>Auto-Modifizierer  
 Die `Auto` Modifizierer weist das Laufzeitmodul an die Zeichenfolge, die basierend auf den Namen der Methode gemäß den Regeln der common Language Runtime (oder Aliasnamen, sofern angegeben) zu konvertieren.  
  
#### <a name="lib-and-alias-keywords"></a>LIB und Alias-Schlüsselwörter  
 Die folgenden Namen der `Function` -Schlüsselwort ist der Name, der das Programm den Zugriff auf die importierte Funktion verwendet. Sie können den tatsächlichen Namen der aufgerufenen Funktion identisch sein oder können Sie eine beliebige gültige Prozedurnamen und wurden, verwenden Sie dann die `Alias` Schlüsselwort, um den tatsächlichen Namen der Funktion geben Sie aufrufen.  
  
 Geben Sie die `Lib` Schlüsselwort, gefolgt von den Namen und Speicherort der DLL, die die Funktion enthält Sie aufrufen. Sie müssen nicht den Pfad in den Verzeichnissen der Windows-System-Dateien anzugeben.  
  
 Verwenden der `Alias` Schlüsselwort, wenn der Name der Funktion, die Sie aufrufen, ist kein gültiger Visual Basic Prozedurname oder steht in Konflikt mit den Namen anderer Elemente in der Anwendung. `Alias` Gibt den eigentlichen Namen der aufgerufenen Funktion an.  
  
#### <a name="argument-and-data-type-declarations"></a>Argument und der Deklarationen von Typen  
 Deklarieren Sie die Argumente und deren Datentypen. Dieser Teil kann schwierig sein, da die Datentypen, die von Windows verwendet in Visual Studio-Datentypen nicht übereinstimmen. Visual Basic wird einen Großteil der Arbeit für Sie durch Konvertieren von Argumenten zu kompatiblen Datentypen einen so genannten *Marshalling*. Sie können explizit steuern, wie für das Marshalling von Argumenten mit der <xref:System.Runtime.InteropServices.MarshalAsAttribute> -Attribut definiert, der <xref:System.Runtime.InteropServices> Namespace.  
  
> [!NOTE]
>  Frühere Versionen von Visual Basic konnten Sie Parameter zu deklarieren `As Any`, d. h. diese Daten eines beliebigen Datentyps verwendet werden konnten. Visual Basic erfordert, dass Sie einen bestimmten Datentyp für alle verwenden `Declare` Anweisungen.  
  
#### <a name="windows-api-constants"></a>Windows-API-Konstanten  
 Einige Argumente sind Kombinationen aus Konstanten. Z. B. die `MessageBox` in dieser exemplarischen Vorgehensweise gezeigten API akzeptiert ein ganzzahliges Argument aufgerufen `Typ` , die steuert, wie das Meldungsfeld angezeigt wird. Sie können den numerischen Wert dieser Konstanten bestimmen, indem Sie untersuchen die `#define` Anweisungen in der Datei WinUser.h. Die numerischen Werte werden im Hexadezimalformat, in der Regel angezeigt, daher sollten Sie mithilfe eines Rechners hinzufügen und Konvertieren in eine Dezimalzahl. Angenommen, Sie die Konstanten für das Format Ausrufezeichen kombinieren möchten `MB_ICONEXCLAMATION` 0x00000030 und die Ja/keine Formatvorlage `MB_YESNO` 0 x 00000004, können Sie addieren der Zahlen und erhalten ein Ergebnis, 0 x 00000034 bzw. 52 Dezimalformat. Decimal Ergebnis direkt verwenden können, es ist besser, deklarieren Sie diese Werte als Konstanten in der Anwendung und kombiniert sie mit der `Or` Operator.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Zum Deklarieren von Konstanten für Windows-API-Aufrufe  
  
1.  Lesen Sie die Dokumentation für die Windows-Funktion, die Sie aufrufen. Bestimmen Sie den Namen der verwendeten Konstanten und den Namen des .h-Datei, die die numerischen Werte für diese Konstanten enthalten.  
  
2.  Verwenden Sie einen Text-Editor wie Editor zum Anzeigen des Inhalts der Headerdatei (. h), und suchen Sie die zugeordneten verwendeten Konstanten Werte. Z. B. die `MessageBox` -API verwendet die Konstante `MB_ICONQUESTION` ein Fragezeichen im Meldungsfeld angezeigt. Die Definition für `MB_ICONQUESTION` steht in WinUser.h und sieht wie folgt aus:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Hinzufügen der entsprechenden `Const` Anweisungen, die der Klasse oder des Moduls auf diese Konstanten für die Anwendung verfügbar zu machen. Zum Beispiel:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Die Prozedur für die DLL aufrufen  
  
1.  Fügen Sie eine Schaltfläche mit dem Namen `Button1` auf den Start des Projekts, und doppelklicken Sie dann auf, um ihren Code anzuzeigen. Der Ereignishandler für die Schaltfläche wird angezeigt.  
  
2.  Hinzufügen von Code für die `Click` -Ereignishandler für die Schaltfläche, die Sie hinzugefügt haben, rufen Sie die Prozedur, und geben Sie die entsprechenden Argumenten:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Drücken Sie F5, um führen Sie das Projekt aus. Das Meldungsfeld wird angezeigt, mit beiden **Ja** und **keine** Antwort Schaltflächen. Klicken Sie auf eine.  
  
#### <a name="data-marshaling"></a>Datenmarshalling  
 Visual Basic automatisch konvertiert die Datentypen der Parameter und Rückgabewerte für Windows-API-Aufrufe, jedoch können Sie die `MarshalAs` Attribut explizit nicht verwaltete Datentypen angeben, die eine API erwartet. Weitere Informationen zum Interop-Marshalling finden Sie unter [Interop-Marshalling](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Deklarieren und MarshalAs in einen API-Aufruf verwenden  
  
1.  Bestimmen Sie den Namen der Funktion sowie deren Argumente Datentypen aufgerufen werden soll, und Wert zurück.  
  
2.  Zur Vereinfachung der Zugriff auf die `MarshalAs` -Attribut enthält, fügen eine `Imports` Anweisungen am Anfang des Codes für die Klasse oder das Modul wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Einen Funktionsprototyp für die importierte Funktion hinzufügen, auf die Klasse oder das Modul, die Sie verwenden, und wenden die `MarshalAs` -Attribut auf die Parameter oder Rückgabewert. Im folgenden Beispiel ein API-Aufruf, der den Typ erwartet `void*` als gemarshallt `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>API-Aufrufe mit DllImport  
 Die `DllImport` Attribut bietet eine zweite Möglichkeit zum Aufruf von Funktionen in DLLs ohne Typbibliotheken. `DllImport` ist weitgehend mit einem `Declare` Anweisung bietet jedoch besser steuern, wie Funktionen aufgerufen werden.  
  
 Sie können `DllImport` mit den meisten Windows-API aufruft, solange der Aufruf an einen freigegebenen verweist (bezeichnet *statische*) Methode. Sie können keine Methoden, die eine Instanz einer Klasse zu erfordern. Im Gegensatz zu `Declare` Anweisungen `DllImport` können keine Aufrufe der `MarshalAs` Attribut.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Eine Windows-API mit dem DllImport-Attribut aufrufen  
  
1.  Öffnen Sie ein neues Windows-Anwendungsprojekt, indem Sie auf **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**. Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie **Windows-Anwendung** aus der Liste der Projektvorlagen für Visual Basic. Das neue Projekt wird angezeigt.  
  
3.  Fügen Sie eine Schaltfläche mit dem Namen `Button2` auf das Startformular.  
  
4.  Doppelklicken Sie auf `Button2` die Codeansicht für das Formular zu öffnen.  
  
5.  Um den Zugriff auf vereinfachen `DllImport`, Hinzufügen einer `Imports` Anweisungen am Anfang des Codes für die Start-Klasse:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Deklarieren Sie eine leere Funktion vorangehenden der `End Class` -Anweisung für das Formular, und die Namen der Funktion `MoveFile`.  
  
7.  Anwenden der `Public` und `Shared` Modifizierer für die Deklaration und Festlegen von Parametern für `MoveFile` basierend auf den Argumenten, die die Windows-API-Funktion verwendet:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     Die Funktion kann ein beliebiger gültiger Prozedurname haben; die `DllImport` -Attribut gibt den Namen in der DLL. Behandelt auch Interop-Marshalling für die Parameter und Rückgabewerte, damit Sie Visual Studio-Datentypen auswählen können, die ähnlich wie die Daten sind der API verwendeten Datentypen.  
  
8.  Anwenden der `DllImport` -Attribut auf die leere Funktion. Der erste Parameter ist der Name und Speicherort der DLL mit der Funktion, die Sie aufrufen. Sie müssen nicht den Pfad in den Verzeichnissen der Windows-System-Dateien anzugeben. Der zweite Parameter ist ein benanntes Argument, das den Namen der Funktion in der Windows-API angibt. In diesem Beispiel wird die `DllImport` -Attribut erzwingt Aufrufe `MoveFile` zur Weiterleitung an `MoveFileW` in KERNEL32. DLL. Die `MoveFileW` -Methode kopiert eine Datei aus dem Pfad `src` auf den Pfad `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Hinzufügen von Code für die `Button2_Click` -Ereignishandler, um die Funktion aufgerufen werden:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Erstellen Sie eine Datei mit dem Namen "Test.txt", und fügen Sie ihn in das Verzeichnis C:\Tmp auf der Festplatte freigeben. Erstellen Sie ggf. die Tmp-Verzeichnis.  
  
11. Drücken Sie F5, um die Anwendung zu starten. Das Hauptformular wird angezeigt.  
  
12. Klicken Sie auf **Button2**. Die Meldung "die Datei erfolgreich verschoben wurde" wird angezeigt, wenn die Datei verschoben werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [Marshallen von Delegaten als Rückrufmethode](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
