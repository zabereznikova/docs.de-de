---
title: Aufruferinformationen (C#) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ffad3d24-2fb7-4641-9124-53b5bc91d339
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 087b547cfc558fb4c82026e9af6ac621809e0ca0
ms.lasthandoff: 03/13/2017

---
# <a name="caller-information-c"></a>Aufruferinformationen (C#)
Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen. Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.  
  
 Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt. Die folgende Tabelle enthält die Aufruferinformationsattribute, die im <xref:System.Runtime.CompilerServices?displayProperty=fullName>-Namespace definiert sind:  
  
|Attribut|Beschreibung|Typ|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Der Methoden- oder Eigenschaftenname des Aufrufers. Weitere Informationen hierzu finden Sie unter [Membernamen](#MEMBERNAMES) weiter unten in diesem Thema.|`String`|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der Aufrufer-Informationsattribute veranschaulicht. Bei jedem Aufruf der `TraceMessage`-Methode werden die Aufruferinformationen als Argumente für optionale Parameter ersetzt.  
  
```csharp  
public void DoProcessing()  
{  
    TraceMessage("Something happened.");  
}  
  
public void TraceMessage(string message,  
        [System.Runtime.CompilerServices.CallerMemberName] string memberName = "",  
        [System.Runtime.CompilerServices.CallerFilePath] string sourceFilePath = "",  
        [System.Runtime.CompilerServices.CallerLineNumber] int sourceLineNumber = 0)  
{  
    System.Diagnostics.Trace.WriteLine("message: " + message);  
    System.Diagnostics.Trace.WriteLine("member name: " + memberName);  
    System.Diagnostics.Trace.WriteLine("source file path: " + sourceFilePath);  
    System.Diagnostics.Trace.WriteLine("source line number: " + sourceLineNumber);  
}  
  
// Sample Output:  
//  message: Something happened.  
//  member name: DoProcessing  
//  source file path: c:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoCS\CallerInfoCS\Form1.cs  
//  source line number: 31  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen einen expliziten Standardwert für jeden optionalen Parameter angeben. Sie können Aufrufer-Informationsattribute nicht auf Parameter anwenden, die nicht als optional festgelegt wurden.  
  
 Durch die Aufrufer-Informationsattribute wird ein Parameter nicht optional. Stattdessen beeinflussen sie den Standardwert, der beim Auslassen des Arguments übergeben wird.  
  
 Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben. Im Gegensatz zu den Ergebnissen der <xref:System.Exception.StackTrace%2A>-Eigenschaft für Ausnahmen werden die Ergebnisse nicht durch Verbergen beeinflusst.  
  
 Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.  
  
###  <a name="MEMBERNAMES"></a> Membernamen  
 Sie können das `CallerMemberName`-Attribut verwenden, um den Membernamen nicht als `String`-Argument für die aufgerufene Methode angeben zu müssen. Auf diese Weise umgehen Sie das Problem, dass durch die **Umgestaltung mit Umbenennung** die `String`-Werte nicht geändert werden. Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:  
  
-   Verwenden der Ablaufverfolgung und der Diagnoseprogramme  
  
-   Das Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle bei der Bindung von Daten. Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann. Ohne das `CallerMemberName`-Attribut müssen Sie den Eigenschaftennamen als Literal angeben.  
  
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
 [Attribute (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)   
 [Allgemeine Attribute (C#)](../../../csharp/programming-guide/concepts/attributes/common-attributes.md)   
 [Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [Programmierkonzepte (C#)](../../../csharp/programming-guide/concepts/index.md)
