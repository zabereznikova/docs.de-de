---
title: Kovarianz und Kontravarianz (C#)
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: 80b4d703bb88d0bf1f7f48236c21b7698017e7f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79169869"
---
# <a name="covariance-and-contravariance-c"></a>Kovarianz und Kontravarianz (C#)
Kovarianz und Kontravarianz in C# ermöglichen die implizite Referenzkonvertierung für Arraytypen, Delegattypen und generische Typargumente. Die Kovarianz behält die Zuweisungskompatibilität bei und die Kontravarianz kehrt sie um.  
  
 Der folgende Code veranschaulicht den Unterschied zwischen Zuweisungskompatibilität, Kovarianz und Kontravarianz.  
  
```csharp  
// Assignment compatibility.
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument
// is assigned to an object instantiated with a less derived type argument.
// Assignment compatibility is preserved.
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;  
```  
  
 Die Kovarianz für Arrays ermöglicht die implizite Konvertierung eines Arrays mit einem stärker abgeleiteten Typ zu einem Array mit einem schwächer abgeleiteten Typ. Dieser Vorgang ist jedoch nicht typsicher, wie im folgenden Codebeispiel gezeigt wird.  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 Die Unterstützung von Kovarianz und Kontravarianz für Methodengruppen ermöglicht es, Methodensignaturen mit Delegattypen abzugleichen. Das bedeutet, dass Sie Delegaten nicht nur Methoden mit übereinstimmenden Signaturen zuweisen können, sondern auch Methoden, die mehrere abgeleitete Typen zurückgeben (Kovarianz) oder die Parameter akzeptieren, die über weniger abgeleitete Typen verfügen, als durch den Delegattyp angegeben wurde (Kontravarianz). Weitere Informationen finden Sie unter [Variance in Delegates (C#) (Varianz in Delegaten (C#))](./variance-in-delegates.md) und [Using Variance in Delegates (C#) (Verwenden von Varianz in Delegaten (C#))](./using-variance-in-delegates.md).  
  
 Im folgenden Codebeispiel wird die Unterstützung von Methodengruppen durch Kovarianz und Kontravarianz veranschaulicht.  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 In .NET Framework 4 oder höher unterstützt C# die Kovarianz und Kontravarianz in generischen Schnittstellen und Delegaten und ermöglicht die implizite Konvertierung von generischen Typparametern. Weitere Informationen finden Sie unter [Variance in Generic Interfaces (C#) (Varianz in generischen Schnittstellen (C#))](./variance-in-generic-interfaces.md) und [Variance in Delegates (C#) (Varianz in Delegaten (C#))](./variance-in-delegates.md).  
  
 Das folgende Codebeispiel zeigt die implizite Verweiskonvertierung bei generischen Schnittstellen.  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 Generische Schnittstellen oder Delegate werden als *variant* bezeichnet, wenn deren generische Parameter als kovariant oder kontravariant deklariert sind. C# ermöglicht es Ihnen, eigene variante Schnittstellen oder Delegate zu erstellen. Weitere Informationen finden Sie unter [Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))](./creating-variant-generic-interfaces.md) und [Variance in Delegates (C#) (Varianz in Delegaten (C#))](./variance-in-delegates.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Varianz in generischen Schnittstellen](./variance-in-generic-interfaces.md)|Erläutert Ko- und Kontravarianz in generischen Schnittstellen und enthält eine Liste der Varianten generischen Schnittstellen in .NET Framework.|  
|[Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))](./creating-variant-generic-interfaces.md)|Zeigt, wie benutzerdefinierte variante Schnittstellen erstellt werden.|  
|[Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))](./using-variance-in-interfaces-for-generic-collections.md)|Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz bei <xref:System.Collections.Generic.IEnumerable%601>- und <xref:System.IComparable%601>-Schnittstellen bei der Wiederverwendung Ihres Codes helfen kann.|  
|[Variance in Delegates (C#) (Varianz bei Delegaten (C#))](./variance-in-delegates.md)|Erläutert Ko- und Kontravarianz in generischen und nicht generischen Delegaten und stellt eine Liste von varianten generischen Delegaten im .NET Framework bereit.|  
|[Using Variance in Delegates (C#) (Verwenden von Varianz in Delegaten (C#))](./using-variance-in-delegates.md)|Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz in nicht generischen Delegaten verwendet werden kann, um Methodensignaturen mit Delegattypen abzugleichen.|  
|[Using Variance for Func and Action Generic Delegates C# (Verwenden von Varianz für die generischen Delegaten Func und Action (C#))](./using-variance-for-func-and-action-generic-delegates.md)|Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz bei `Func`- und `Action`-Delegaten bei der Wiederverwendung Ihres Codes helfen kann.|
