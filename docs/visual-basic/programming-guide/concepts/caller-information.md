---
title: Aufruferinformationen
ms.date: 07/20/2015
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
ms.openlocfilehash: 7c87b540a68f4d0219918fed66de6c1b635104a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349476"
---
# <a name="caller-information-visual-basic"></a>Caller Information (Visual Basic)
Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen. Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.  
  
 Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt. In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:  
  
|Attribut|Beschreibung|Geben Sie Folgendes ein:|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Der Methoden- oder Eigenschaftenname des Aufrufers. Weitere Informationen hierzu finden Sie unter [Membernamen](#MEMBERNAMES) weiter unten in diesem Thema.|`String`|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der Aufrufer-Informationsattribute veranschaulicht. Bei jedem Aufruf der `TraceMessage`-Methode werden die Aufruferinformationen als Argumente für optionale Parameter ersetzt.  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen einen expliziten Standardwert für jeden optionalen Parameter angeben. Sie können Aufrufer-Informationsattribute nicht auf Parameter anwenden, die nicht als optional festgelegt wurden.  
  
 Durch die Aufrufer-Informationsattribute wird ein Parameter nicht optional. Stattdessen beeinflussen sie den Standardwert, der beim Auslassen des Arguments übergeben wird.  
  
 Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben. Im Gegensatz zu den Ergebnissen der <xref:System.Exception.StackTrace%2A>-Eigenschaft für Ausnahmen werden die Ergebnisse nicht durch Verbergen beeinflusst.  
  
 Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.  
  
### <a name="MEMBERNAMES"></a> Membernamen  
 Sie können das `CallerMemberName`-Attribut verwenden, um den Membernamen nicht als `String`-Argument für die aufgerufene Methode angeben zu müssen. Auf diese Weise umgehen Sie das Problem, dass durch die **Umgestaltung mit Umbenennung** die `String`-Werte nicht geändert werden. Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:  
  
- Verwenden der Ablaufverfolgung und der Diagnoseprogramme  
  
- Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle beim Binden von Daten Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann. Ohne das `CallerMemberName`-Attribut müssen Sie den Eigenschaftennamen als Literal angeben.  
  
 Im folgenden Diagramm sind die Membernamen aufgeführt, die beim Verwenden des `CallerMemberName`-Attributs zurückgegeben werden.  
  
|Aufrufe erfolgen in|Ergebnis des Membernamens|  
|-------------------------|------------------------|  
|Methode, Eigenschaft oder Ereignis|Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.|  
|Konstruktor|Die Zeichenfolge ".ctor"|  
|Statischer Konstruktor|Die Zeichenfolge ".cctor"|  
|Destruktor|Die Zeichenfolge "Finalize"|  
|Benutzerdefinierte Operatoren oder Konvertierungen|Der generierte Name für den Member, beispielsweise "op_Addition".|  
|Attributkonstruktor|Der Name des Members, auf den das Attribut angewendet wird. Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.|  
|Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)|Der Standardwert des optionalen Parameters.|  
  
## <a name="see-also"></a>Siehe auch

- [Attribute (Visual Basic)](../../../visual-basic/language-reference/attributes.md)
- [Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Gemeinsame Attribute (Visual Basic))
- [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Programming Concepts (Visual Basic) (Programmierkonzepte (Visual Basic))](../../../visual-basic/programming-guide/concepts/index.md)
