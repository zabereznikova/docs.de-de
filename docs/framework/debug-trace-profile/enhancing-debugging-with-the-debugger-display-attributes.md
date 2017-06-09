---
title: "Enhancing Debugging with the Debugger Display Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "debugger, display attributes"
  - "DebuggerTypeProxyAttribute attribute"
  - "debugging [.NET Framework], debugger display attributes"
  - "DebuggerDisplayAttribute attribute"
  - "display attributes for debugger"
  - "DebuggerBrowsableAttribute attribute"
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Enhancing Debugging with the Debugger Display Attributes
Debuggeranzeigeattribute ermöglichen es einem Entwickler eines Typs, der das Laufzeitverhalten dieses Typs festlegt und am besten damit vertraut ist, auch anzugeben, wie dieser Typ in einem Debugger angezeigt wird.  Außerdem können Debuggeranzeigeattribute, die die `Target`\-Eigenschaft bereitstellen, von Benutzern, die den Quellcode nicht kennen, auf der Assemblyebene angewendet werden.  Das <xref:System.Diagnostics.DebuggerDisplayAttribute>\-Attribut steuert die Anzeige eines Typs oder eines Members in den Debuggervariablenfenstern.  Das <xref:System.Diagnostics.DebuggerBrowsableAttribute>\-Attribut bestimmt, ob und wie ein Feld oder eine Eigenschaft in den Debuggervariablenfenstern angezeigt wird.  Das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>\-Attribut gibt einen Ersatztyp \(einen Proxy\) für einen Typ an und ändert die Art, in der der Typ in Debuggerfenstern angezeigt wird.  Wenn Sie eine Variable mit einem Proxy \(einem Ersatztyp\) anzeigen, wird der Proxy stellvertretend für den ursprünglichen Typ im Anzeigefenster des Debuggers angezeigt. Im Debuggervariablenfenster werden nur die öffentlichen Member des Proxytyps angezeigt.  Private Member werden nicht angezeigt.  
  
## Verwenden von DebuggerDisplayAttribute  
 Der <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A>\-Konstruktor verfügt über ein einzelnes Argument: eine Zeichenfolge, die in der Spalte Wert für Instanzen des Typs angezeigt wird.  Diese Zeichenfolge kann geschweifte Klammern \({ und }\) enthalten.  Der Text innerhalb eines Paares geschweifter Klammern wird als Ausdruck ausgewertet.  So wird beispielsweise mit dem folgenden C\#\-Code "Count \= 4" angezeigt, wenn das Pluszeichen \(\+\) ausgewählt wird, um eine Instanz von `MyHashtable` in der Debuggeranzeige zu erweitern.  
  
```  
[DebuggerDisplay("Count = {count}")]  
class MyHashtable  
{  
    public int count = 4;  
}  
```  
  
 Es werden keine Attribute verarbeitet, die auf Eigenschaften angewendet werden, auf die im Ausdruck verwiesen wird.  Für den C\#\-Compiler ist ein allgemeiner Ausdruck zulässig, der nur über impliziten Zugriff auf diesen Verweis für die aktuelle Instanz des Zieltyps verfügt.  Der Ausdruck ist eingeschränkt. Der Zugriff auf Aliase, lokale Variablen oder Zeiger ist nicht möglich.  In C\#\-Code können Sie in den geschweiften Klammern einen allgemeinen Ausdruck verwenden, der lediglich über impliziten Zugriff auf den `this`\-Zeiger für die aktuelle Instanz des Zieltyps verfügt.  
  
 Falls beispielsweise ein überschriebenes `ToString()` für ein C\#\-Objekt vorhanden ist, ruft der Debugger die Überschreibung auf und zeigt deren Ergebnis anstelle des standardmäßigen `{<typeName>}.` an. Auf diese Weise müssen Sie nicht <xref:System.Diagnostics.DebuggerDisplayAttribute> verwenden, falls Sie `ToString()` überschrieben haben.  Wenn Sie beides verwenden, hat das <xref:System.Diagnostics.DebuggerDisplayAttribute>\-Attribut Vorrang gegenüber der `ToString()`\-Überschreibung.  
  
## Verwenden von DebuggerBrowsableAttribute  
 Wenden Sie das <xref:System.Diagnostics.DebuggerBrowsableAttribute> auf ein Feld oder eine Eigenschaft an, um anzugeben, wie das Feld oder die Eigenschaft im Debuggerfenster angezeigt wird.  Der Konstruktor für dieses Attribut akzeptiert einen der <xref:System.Diagnostics.DebuggerBrowsableState>\-Enumerationswerte, der einen der folgenden Zustände angibt:  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> gibt an, dass der Member nicht im Datenfenster angezeigt wird.  Bei Verwendung dieses Werts für das <xref:System.Diagnostics.DebuggerBrowsableAttribute> eines Felds wird beispielsweise das Feld aus der Hierarchie entfernt. Das Feld wird nicht angezeigt, wenn Sie den einschließenden Typ durch Klicken auf das Pluszeichen \(\+\) für die Typeninstanz erweitern.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> gibt an, dass der Member angezeigt, aber nicht standardmäßig erweitert wird.  Dies ist das Standardverhalten.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> gibt an, dass der Member selbst nicht angezeigt wird. Wenn es sich um ein Array oder eine Auflistung handelt, werden jedoch die konstituierenden Objekte angezeigt.  
  
> [!NOTE]
>  Das <xref:System.Diagnostics.DebuggerBrowsableAttribute> wird von Visual Basic in .NET Framework, Version 2.0, nicht unterstützt.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie das <xref:System.Diagnostics.DebuggerBrowsableAttribute> verwendet wird, damit die nachfolgende Eigenschaft für die Klasse nicht im Debuggerfenster angezeigt wird.  
  
```  
[DebuggerBrowsable(DebuggerBrowsableState.Never)]  
public static string y = "Test String";  
```  
  
## Verwenden von DebuggerTypeProxy  
 Verwenden Sie das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>\-Attribut, wenn Sie die Debuggeransicht eines Typs, nicht jedoch den Typ selbst, grundlegend ändern müssen.  Das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>\-Attribut wird verwendet, um einen Anzeigeproxy für einen Typ anzugeben, damit die Ansicht des Typs bei der Entwicklung angepasst werden kann.  Wie auch <xref:System.Diagnostics.DebuggerDisplayAttribute> kann dieses Attribut auf der Assemblyebene verwendet werden. In diesem Fall legt die <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A>\-Eigenschaft den Typ fest, für den der Proxy verwendet wird.  Es wird empfohlen, dass mit diesem Attribut ein privater geschachtelter Typ angegeben wird, der innerhalb des Typs vorhanden ist, auf den das Attribut angewendet wird.  Eine Ausdrucksauswertung, die beim Anzeigen eines Typs das Überprüfen von Typ\-Viewern unterstützt.  Wenn das Attribut gefunden wird, ersetzt die Ausdrucksauswertung den Anzeigeproxytyp für den Typ, auf den das Attribut angewendet wird.  
  
 Wenn das <xref:System.Diagnostics.DebuggerTypeProxyAttribute> vorhanden ist, werden im Variablenfenster des Debuggers nur die öffentlichen Member des Proxytyps angezeigt.  Private Member werden nicht angezeigt.  Das Verhalten des Datenfensters ändert sich nicht, wenn Ansichten durch Attribute modifiziert werden.  
  
 Um unnötige Leistungseinbußen zu vermeiden, werden die Attribute des Ansichtsproxys erst verarbeitet, wenn das Objekt erweitert wird, entweder durch Klicken auf das Pluszeichen \(\+\) neben dem Typ im Datenfenster oder durch Anwendung des <xref:System.Diagnostics.DebuggerBrowsableAttribute>\-Attributs.  Deshalb wird empfohlen, keine Attribute auf den Anzeigetyp anzuwenden.  Attribute können und sollen im Text des Anzeigetyps angewendet werden.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Diagnostics.DebuggerTypeProxyAttribute> verwendet wird, um einen Typ als Debuggeranzeigeproxy anzugeben.  
  
```  
  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable : Hashtable  
{  
    private const string TestString =   
        "This should not appear in the debug window.";  
  
    internal class HashtableDebugView  
    {  
        private Hashtable hashtable;  
        public const string TestStringProxy =   
            "This should appear in the debug window.";  
  
        // The constructor for the type proxy class must have a   
        // constructor that takes the target type as a parameter.  
        public HashtableDebugView(Hashtable hashtable)  
        {  
            this.hashtable = hashtable;  
        }  
    }  
}  
```  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Codebeispiel kann in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] angezeigt werden. Sie sehen dann die jeweiligen Auswirkungen, wenn die Attribute <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute> und <xref:System.Diagnostics.DebuggerTypeProxyAttribute> angewendet werden.  
  
### Code  
 [!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
 [!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
 [!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]  
  
## Siehe auch  
 <xref:System.Diagnostics.DebuggerDisplayAttribute>   
 <xref:System.Diagnostics.DebuggerBrowsableAttribute>   
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>