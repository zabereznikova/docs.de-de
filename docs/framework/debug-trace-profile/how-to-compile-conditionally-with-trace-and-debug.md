---
title: 'Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen'
description: Erfahren Sie, wie Sie bedingt mit den bedingten Attributen für Ablauf Verfolgung und Debuggen kompilieren, wenn Sie eine .NET-Anwendung
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
ms.openlocfilehash: 895e39593b5e84d708392d3d994267b25bc4eeea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244170"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a>Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen

Beim Debuggen einer Anwendung während der Entwicklung wird sowohl die Ablaufverfolgungsausgabe als auch die Debugausgabe im Ausgabefenster von Visual Studio angezeigt. Allerdings müssen Sie Ihre instrumentierten Anwendungen mit aktivierter **TRACE**-Compilerdirektive kompilieren, um Ablaufverfolgungsfunktionen in eine bereitgestellte Anwendung aufzunehmen. Dadurch kann der Ablaufverfolgungscode in die Releaseversion der Anwendung kompiliert werden. Wenn Sie die **TRACE**-Anweisung nicht aktivieren, wird der gesamte Ablaufverfolgungscode bei der Kompilierung ignoriert und nicht in den ausführbaren Code aufgenommen, den Sie bereitstellen.  
  
 Sowohl die Ablaufverfolgungsmethoden als auch die Debugmethoden weisen zugeordnete Conditional-Attribute auf. Wenn das Conditional-Attribut für die Ablaufverfolgung beispielsweise **TRUE** ist, werden alle Ablaufverfolgungsanweisungen in eine Assembly (eine kompilierte EXE- oder DLL-Datei) aufgenommen. Ist das Conditional-Attribut **TRACE** hingegen **FALSE**, werden die Ablaufverfolgungsanweisungen nicht aufgenommen.  
  
 Für einen Build kann das Conditional-Attribut **Trace** oder **Debug** aktiviert sein oder beide Conditional-Attribute oder keines von beiden. Daher gibt es vier Typen von Builds: **Debug**, **Trace**, beide oder keines von beiden. Manche Releasebuilds für die Produktionsbereitstellung enthalten keines von beiden, und die meisten Debugbuilds enthalten beide.  
  
 Sie können die Compilereinstellungen für die Anwendung auf verschiedene Arten angeben:  
  
- Eigenschaftenseiten  
  
- Die Befehlszeile  
  
- **#CONST** (für Visual Basic) und **#define** (für C#)  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a>So ändern Sie die Kompilierungseinstellungen im Dialogfeld "Eigenschaftenseiten"  
  
1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten.  
  
2. Wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.  
  
    - Klicken Sie in Visual Basic im linken Bereich der Eigenschaftenseite auf die Registerkarte **Kompilieren**, und klicken Sie dann auf die Schaltfläche **Erweiterte Kompilierungsoptionen**, um das Dialogfeld **Erweiterte Kompilierungsoptionen** anzuzeigen. Aktivieren Sie die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen. Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.  
  
    - Klicken Sie in C# auf die Registerkarte **Erstellen** im linken Bereich der Eigenschaftenseite, und aktivieren Sie dann die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen. Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a>So kompilieren Sie instrumentierten Code über die Befehlszeile  
  
1. Legen Sie über die Befehlszeile einen bedingten Compilerschalter fest. Der Compiler integriert Ablaufverfolgungs- oder Debugcode in die ausführbare Datei.  
  
     Beispielsweise wird der Ablaufverfolgungscode in eine kompilierte ausführbare Datei aufgenommen, wenn die folgende Compileranweisung über die Befehlszeile eingegeben wird:  
  
     Für Visual Basic: **vbc -r:System.dll-d:Trace = true-d:Debug = FALSE MyApplication. vb**  
  
     Für c#: **csc -r:System.dll-d:Trace-d:Debug = FALSE MyApplication.cs**  
  
    > [!TIP]
    > Lassen Sie einen Leerraum zwischen den Dateinamen, um mehr als eine Anwendungsdatei zu kompilieren, z.B. **MyApplication1.vb MyApplication2.vb MyApplication3.vb** oder **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.  
  
     Die in den obigen Beispielen verwendeten Anweisungen zur bedingten Kompilierung bedeuten Folgendes:  
  
    |Anweisung|Bedeutung|  
    |---------------|-------------|  
    |`vbc`|Visual Basic-Compiler|  
    |`csc`|C#-Compiler|  
    |`-r:`|Verweist auf eine externe Assembly (EXE oder DLL)|  
    |`-d:`|Definiert ein Symbol für bedingte Kompilierung|  
  
    > [!NOTE]
    > Sie müssen TRACE oder DEBUG mit Großbuchstaben schreiben. Geben Sie an der Eingabeaufforderung `vbc /?` (für Visual Basic) oder `csc /?` (für C#) ein, um weitere Informationen zu den Befehlen zur bedingten Kompilierung anzuzeigen. Weitere Informationen finden Sie unter [Erstellen von der Befehlszeile aus](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) oder [Aufrufen des Befehlszeilencompilers](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a>So führen Sie die bedingte Kompilierung mit #CONST oder #define durch  
  
1. Geben Sie am Anfang der Quellcodedatei die entsprechende Anweisung für Ihre Programmiersprache ein.  
  
    |Sprache|-Anweisung.|Ergebnis|  
    |--------------|---------------|------------|  
    |**Visual Basic**|**#CONST TRACE = true**|Aktiviert die Ablaufverfolgung|  
    ||**#CONST TRACE = false**|Deaktiviert die Ablaufverfolgung|  
    ||**#CONST DEBUG = true**|Aktiviert das Debuggen|  
    ||**#CONST DEBUG = false**|Deaktiviert das Debuggen|  
    |**C#**|**#define TRACE**|Aktiviert die Ablaufverfolgung|  
    ||**#undefine TRACE**|Deaktiviert die Ablaufverfolgung|  
    ||**#define DEBUG**|Aktiviert das Debuggen|  
    ||**#undefine DEBUG**|Deaktiviert das Debuggen|  
  
### <a name="to-disable-tracing-or-debugging"></a>So deaktivieren Sie die Ablaufverfolgung oder das Debuggen  
  
Löschen Sie die Compilerdirektive aus dem Quellcode.  
  
\- oder -  
  
Kommentieren Sie die Compileranweisung aus.  
  
> [!NOTE]
> Wenn Sie kompilieren möchten, können Sie entweder **Erstellen** aus dem Menü **Erstellen** auswählen oder die Befehlszeilenmethode verwenden, allerdings ohne Eingabe von **d:** zum Definieren der Symbole für bedingte Kompilierung.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung und Instrumentieren von Anwendungen](tracing-and-instrumenting-applications.md)
- [Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md)
- [Ablaufverfolgungsschalter](trace-switches.md)
- [Ablaufverfolgungslistener](trace-listeners.md)
- [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md)
- [Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [Vorgehensweise: Aufrufen des Befehlszeilencompilers](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
