---
title: "Walkthrough: Calling Windows APIs (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DLLs, calling"
  - "Windows API, walkthroughs"
  - "platform invoke, walkthroughs"
  - "API calls, walkthroughs [Visual Basic]"
  - "Windows API, calling"
  - "walkthroughs [Visual Basic], API calls"
  - "DllImport attribute, calling Windows API"
  - "Declare statement, declaring DLL functions"
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Walkthrough: Calling Windows APIs (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Windows\-APIs sind DLLs \(Dynamic Link Libraries\), die Bestandteil des Betriebssystems Windows sind.  Verwenden Sie DLLs, wenn das Schreiben eigener Prozeduren für bestimmte Aufgaben zu aufwendig ist.  Windows bietet z. B. die Funktion `FlashWindowEx`, mit der Sie die Farbe einer Titelleiste für eine Anwendung von Hell nach Dunkel wechseln lassen können.  
  
 Der Vorteil der Verwendung von Windows\-APIs im Code ist die verkürzte Entwicklungszeit, da Sie Dutzende hilfreiche und bereits verfasste Funktionen verwenden können.  Ein Nachteil von Windows\-APIs ist, dass die Verwendung möglicherweise schwierig ist und Probleme kaum abgefangen werden können.  
  
 Windows\-APIs stellen eine besondere Kategorie der Interoperabilität dar.  Windows\-APIs verwenden keinen verwalteten Code, verfügen nicht über integrierte Typbibliotheken und verwenden andere Datentypen als Visual Studio.  Aufgrund dieser Unterschiede und weil Windows\-APIs keine COM\-Objekte sind, erfolgt die Zusammenarbeit zwischen Windows\-APIs und [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] über die Plattformaktivierung \(PInvoke\).  Die Plattformaktivierung ist ein Dienst, mit dem verwalteter Code nicht verwaltete Funktionen aufrufen kann, die in DLLs implementiert sind.  Weitere Informationen finden Sie unter [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md).  Sie können PInvoke in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] entweder mit der `Declare`\-Anweisung oder durch Anwenden des `DllImport`\-Attributs auf eine leere Prozedur verwenden.  
  
 Windows\-API\-Aufrufe waren in der Vergangenheit ein wichtiger Bestandteil der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programmierung, sind aber bei [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] selten erforderlich.  Verwenden Sie zum Ausführen von Aufgaben nach Möglichkeit immer verwalteten Code von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] anstelle von Windows\-API\-Aufrufen.  Diese exemplarische Vorgehensweise enthält Informationen über die Situationen, in denen die Verwendung von Windows\-APIs erforderlich ist.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## API\-Aufrufe mit "Declare"  
 Aufrufe von Windows\-APIs erfolgen im Allgemeinen über die `Declare`\-Anweisung.  
  
#### So deklarieren Sie eine DLL\-Prozedur  
  
1.  Bestimmen Sie den Namen der aufzurufenden Funktion und der Argumente, Argumenttypen und Rückgabewerte sowie den Namen und Speicherort der DLL, die die Funktion enthält.  
  
    > [!NOTE]
    >  Vollständige Informationen über Windows\-APIs finden Sie in der Win32\-SDK\-Dokumentation im Platform SDK Windows\-API.  Weitere Informationen über die von Windows\-APIs verwendeten Konstanten finden Sie im Platform SDK in Headerdateien wie "Windows.h".  
  
2.  Öffnen Sie ein neues Windows\-Anwendungsprojekt, indem Sie im Menü **Datei** erst auf **Neu** und dann auf **Projekt** klicken.  Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Wählen Sie in der Liste der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Projektvorlagen **Windows\-Anwendung** aus.  Das neue Projekt wird angezeigt.  
  
4.  Fügen Sie die folgende `Declare`\-Funktion entweder der Klasse oder dem Modul hinzu, in der bzw. dem Sie die DLL verwenden möchten:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#9)]  
  
### Bestandteile der Declare\-Anweisung  
 Die `Declare`\-Anweisung enthält folgende Elemente:  
  
#### Auto\-Modifizierer  
 Der `Auto`\-Modifizierer weist die Common Language Runtime an, die Zeichenfolge entsprechend dem Methodennamen \(oder Aliasnamen, sofern angegeben\) nach den Regeln der Common Language Runtime zu konvertieren.  
  
#### Schlüsselwörter "Lib" und "Alias"  
 Anhand des Namens, der auf das Schlüsselwort `Function` folgt, greift das Programm auf die importierte Funktion zu.  Dieser kann mit dem eigentlichen Namen der aufgerufenen Funktion übereinstimmen. Sie können aber einen beliebigen gültigen Prozedurnamen verwenden und anschließend mit dem Schlüsselwort `Alias` den eigentlichen Namen der aufgerufenen Funktionen angeben.  
  
 Geben Sie das `Lib`\-Schlüsselwort an, gefolgt von dem Namen und Speicherort der DLL mit der aufgerufenen Funktion.  Sie brauchen den Pfad zu Dateien in Windows\-Systemverzeichnissen nicht anzugeben.  
  
 Verwenden Sie das `Alias`\-Schlüsselwort, wenn der Name der aufgerufenen Funktion kein gültiger [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Prozedurname ist oder mit dem Namen anderer Elemente in der Anwendung in Konflikt steht.  `Alias` gibt den tatsächlichen Namen der aufgerufenen Funktion an.  
  
#### Argument\- und Datentypdeklarationen  
 Deklarieren Sie die Argumente und deren Datentypen.  Dieser Teil kann mit einigen Herausforderungen verbunden sein, da die Windows\-Datentypen nicht den Visual Studio\-Datentypen entsprechen.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] nimmt Ihnen einen Großteil der Arbeit ab, indem Argumente in kompatible Datentypen konvertiert werden. Dieser Prozess wird als *Marshalling* bezeichnet.  Sie können das Marshalling der Argumente explizit steuern, indem Sie das im <xref:System.Runtime.InteropServices>\-Namespace definierte <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut verwenden.  
  
> [!NOTE]
>  Bei älteren Versionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] konnten Sie Parameter als `As Any` deklarieren, d. h., dass Daten eines beliebigen Datentyps verwendet werden konnten.  Bei [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] müssen Sie einen bestimmten Datentyp für alle `Declare`\-Anweisungen verwenden.  
  
#### Windows\-API\-Konstanten  
 Einige Argumente sind Kombinationen von Konstanten.  Die in dieser exemplarischen Vorgehensweise gezeigte `MessageBox`\-API übernimmt z. B. das integer\-Argument `Typ`, das die Anzeige des Meldungsfelds steuert.  Sie können den numerischen Wert dieser Konstanten bestimmen, indem Sie die `#define`\-Anweisungen in der Datei "WinUser.h" untersuchen.  Die numerischen Werte werden im Allgemeinen im Hexadezimalformat angezeigt. Es empfiehlt sich daher, diese mit einem Rechner zu addieren und in Dezimalzahlen umzuwandeln.  Wenn Sie z. B. die Konstanten für das Format mit Ausrufezeichen `MB_ICONEXCLAMATION` 0x00000030 und das Format mit Ja\/Nein\-Schaltflächen `MB_YESNO` 0x00000004 kombinieren möchten, können Sie die Zahlen addieren, und erhalten so als Ergebnis 0x00000034 bzw. im Dezimalformat 52.  Sie können das Dezimalergebnis direkt verwenden, es wird aber empfohlen, diese Werte als Konstanten in der Anwendung zu deklarieren und mit dem Operator `Or` zu kombinieren.  
  
###### So deklarieren Sie Konstanten für Windows\-API\-Aufrufe  
  
1.  Schlagen Sie in der Dokumentation für die aufgerufene Windows\-Funktion nach.  Bestimmen Sie den Namen der verwendeten Konstanten und den Namen der H\-Datei, die die numerischen Werte für diese Konstanten enthält.  
  
2.  Öffnen Sie die Headerdatei \(H\-Datei\) in einem Text\-Editor \(z. B. Windows Editor\), und suchen Sie die den verwendeten Konstanten zugeordneten Werte.  Die `MessageBox`\-API verwendet z. B. die `MB_ICONQUESTION`\-Konstante zum Anzeigen eines Fragezeichens im Meldungsfeld.  Die Definition für `MB_ICONQUESTION` steht in WinUser.h und lautet folgendermaßen:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Fügen Sie der Klasse oder dem Modul entsprechende `Const`\-Anweisungen hinzu, um diese Konstanten in der Anwendung verfügbar zu machen.  Beispiele:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#11)]  
  
###### So rufen Sie die DLL\-Prozedur auf  
  
1.  Fügen Sie dem Startformular des Projekts die Schaltfläche `Button1` hinzu, und doppelklicken Sie anschließend darauf, um ihren Code anzuzeigen.  Der Ereignishandler für die Schaltfläche wird angezeigt.  
  
2.  Fügen Sie im `Click`\-Ereignishandler Code für die Schaltfläche hinzu, die Sie für den Aufruf der Prozedur hinzugefügt haben, und geben Sie die entsprechenden Argumente an:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#12)]  
  
3.  Führen Sie das Projekt aus, indem Sie F5 drücken.  Das Meldungsfeld wird mit den Antwortschaltflächen **Ja** und **Nein** angezeigt.  Klicken Sie auf eine der beiden Schaltflächen.  
  
#### Datenmarshalling  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] konvertiert die Datentypen von Parametern und Rückgabewerten für Windows\-API\-Aufrufe automatisch. Sie können aber mit dem `MarshalAs`\-Attribut explizit nicht verwaltete Datentypen angeben, die von einer API erwartet werden.  Weitere Informationen zum Interop\-Marshalling finden Sie unter [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
###### So verwenden Sie "Declare" und "MarshalAs" in einem API\-Aufruf  
  
1.  Bestimmen Sie den Namen der aufzurufenden Funktion sowie deren Argumente, Datentypen und Rückgabewerte.  
  
2.  Um den Zugriff auf das `MarshalAs`\-Attribut zu vereinfachen, fügen Sie am Anfang des Codes für die Klasse oder das Modul wie im folgenden Beispiel gezeigt eine `Imports`\-Anweisung ein:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#13)]  
  
3.  Fügen Sie in der verwendeten Klasse oder im verwendeten Modul einen Funktionsprototyp für die importierte Funktion ein, und wenden Sie das `MarshalAs`\-Attribut auf die Parameter oder den Rückgabewert an.  Im folgenden Beispiel wird ein API\-Aufruf, der den Typ `void*` erwartet, als `AsAny` gemarshallt:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#14)]  
  
## API\-Aufrufe mit "DllImport"  
 Das `DllImport`\-Attribut bietet eine zweite Möglichkeit, Funktionen in DLLs ohne Typbibliotheken aufzurufen.  `DllImport` entspricht ungefähr der Verwendung einer `Declare`\-Anweisung, es lässt sich damit aber die Art des Funktionsaufrufs besser steuern.  
  
 Sie können `DllImport` bei fast allen Windows\-API\-Aufrufen verwenden, sofern der Aufruf einer freigegebenen \(auch als *static* bezeichneten\) Methode gilt.  Sie können keine Methoden verwenden, die eine Instanz einer Klasse verlangen.  Im Gegensatz zu `Declare`\-Anweisungen kann bei `DllImport`\-Aufrufen nicht das `MarshalAs`\-Attribut verwendet werden.  
  
#### So rufen Sie eine Windows\-API mit dem DllImport\-Attribut auf  
  
1.  Öffnen Sie ein neues Windows\-Anwendungsprojekt, indem Sie im Menü **Datei** erst auf **Neu** und dann auf **Projekt** klicken.  Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Wählen Sie in der Liste der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Projektvorlagen **Windows\-Anwendung** aus.  Das neue Projekt wird angezeigt.  
  
3.  Fügen Sie dem Startformular die Schaltfläche `Button2` hinzu.  
  
4.  Doppelklicken Sie auf `Button2`, um die Codeansicht für das Formular anzuzeigen.  
  
5.  Um den Zugriff auf `DllImport` zu vereinfachen, fügen Sie am Anfang des Codes für die Startformularklasse eine `Imports`\-Anweisung ein:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#13)]  
  
6.  Deklarieren Sie vor der `End Class`\-Anweisung des Formulars eine leere Funktion mit dem Namen `MoveFile`.  
  
7.  Weisen Sie der Funktionsdeklaration den `Public`\-Modifizierer und den `Shared`\-Modifizierer zu, und legen Sie, entsprechend den von der Windows\-API\-Funktion verwendeten Argumenten, Parameter für `MoveFile` fest:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#16)]  
  
     Die Funktion kann jeden gültigen Prozedurnamen besitzen. Das `DllImport`\-Attribut gibt den Namen in der DLL an.  Es behandelt auch das Interop\-Marshalling für die Parameter und Rückgabewerte, sodass Sie Visual Studio\-Datentypen wählen können, die mit den von der API verwendeten Datentypen übereinstimmen.  
  
8.  Weisen Sie der leeren Funktion das `DllImport`\-Attribut zu.  Der erste Parameter ist der Name und der Speicherort der DLL mit der aufzurufenden Funktion.  Sie brauchen den Pfad zu Dateien in Windows\-Systemverzeichnissen nicht anzugeben.  Der zweite Parameter ist ein benanntes Argument, das den Namen der Funktion in der Windows\-API angibt.  In diesem Beispiel erzwingt das `DllImport`\-Attribut, dass Aufrufe von `MoveFile` an `MoveFileW` in KERNEL32.DLL weitergeleitet werden.  Die `MoveFileW`\-Methode kopiert eine Datei aus dem Pfad `src` in den Pfad `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#17)]  
  
9. Fügen Sie dem `Button2_Click`\-Ereignishandler Code hinzu, um die Funktion aufzurufen:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/vbvbalrinterop/Class1.vb#18)]  
  
10. Erstellen Sie die Datei Test.txt, und speichern Sie diese auf der Festplatte im Verzeichnis C:\\Tmp.  Erstellen Sie ggf. das Verzeichnis "Tmp".  
  
11. Drücken Sie F5, um die Anwendung zu starten.  Das Hauptformular wird angezeigt.  
  
12. Klicken Sie auf **Button2**.  Die Meldung "The file was moved successfully" wird angezeigt, sofern die Datei verschoben werden kann.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Creating Prototypes in Managed Code](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)   
 [Marshaling a Delegate as a Callback Method](../Topic/Marshaling%20a%20Delegate%20as%20a%20Callback%20Method.md)