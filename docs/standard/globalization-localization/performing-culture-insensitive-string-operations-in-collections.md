---
title: "Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenoperationen in Auflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ArrayList.Sort-Methode"
  - "CaseInsensitiveComparer-Klasse, Verwenden"
  - "CaseInsensitiveHashCodeProvider-Klasse, Verwenden"
  - "Auflistungen [.NET Framework], Kulturunabhängige Zeichenfolgenoperationen"
  - "CollectionsUtil.CreateCaseInsensitiveHashtable-Methode"
  - "culture-Parameter"
  - "Kulturunabhängige Zeichenfolgenoperationen, Auflistungen"
  - "SortedList-Klasse, Kulturunabhängige Zeichenfolgenoperationen"
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Durchf&#252;hren kulturunabh&#228;ngiger Zeichenfolgenoperationen in Auflistungen
Der <xref:System.Collections>\-Namespace enthält Klassen und Member, die als Standardeinstellung ein kulturabhängiges Verhalten bereitstellen.  Die Standardkonstruktoren für die <xref:System.Collections.CaseInsensitiveComparer>\-Klasse und die <xref:System.Collections.CaseInsensitiveHashCodeProvider>\-Klasse initialisieren mit der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName>\-Eigenschaft eine neue Instanz.  Alle Überladungen der [CollectionsUtil.CreateCaseInsensitiveHashTable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)\-Methode erstellen eine neue Instanz der <xref:System.Collections.Hashtable>\-Klasse und verwenden dabei standardmäßig die `Thread.CurrentCulture`\-Eigenschaft.  Überladungen der <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName>\-Methode führen standardmäßig kulturabhängige Sortierungen mit `Thread.CurrentCulture` durch.  Wenn als Schlüssel Zeichenfolgen verwendet werden, kann das Sortieren und Suchen in einer <xref:System.Collections.SortedList> durch `Thread.CurrentCulture` beeinflusst werden.  Befolgen Sie die Verwendungsempfehlungen in diesem Abschnitt, um aus diesen Klassen und Methoden im `Collections`\-Namespace kulturunabhängige Ergebnisse abzurufen.  
  
 **Hinweis** Wenn Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> an eine Vergleichsmethode übergeben, wird ein kulturunabhängiger Vergleich ausgeführt.  Es wird jedoch kein nicht linguistischer Vergleich ausgeführt, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen.  Eine Grundlage für Sicherheitsentscheidungen anhand des Vergleichsergebnisses ist dadurch nicht gegeben.  Wenn Sie einen nicht linguistischen Vergleich oder eine Grundlage für ergebnisbasierte Sicherheitsentscheidungen benötigen, muss die Anwendung eine Vergleichsmethode verwenden, die einen <xref:System.StringComparison>\-Wert akzeptiert.  Die Anwendung muss dann <xref:System.StringComparison> übergeben.  
  
## Verwenden der CaseInsensitiveComparer\-Klasse und der CaseInsensitiveHashCodeProvider\-Klasse  
 Die Standardkonstruktoren für `CaseInsensitiveHashCodeProvider` und `CaseInsensitiveComparer` initialisieren eine neue Instanz der Klasse mit der `Thread.CurrentCulture`, was zu kulturabhängigem Verhalten führt.  Im folgenden Codebeispiel wird der Konstruktor für eine `Hashtable` veranschaulicht, die kulturabhängig ist, da die Standardkonstruktoren für `CaseInsensitiveHashCodeProvider` und `CaseInsensitiveComparer` verwendet werden.  
  
```vb  
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)  
  
```  
  
```csharp  
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);  
```  
  
 Wenn Sie mit der `CaseInsensitiveComparer`\-Klasse und der `CaseInsensitiveHashCodeProvider`\-Klasse eine kulturunabhängige `Hashtable`erstellen möchten, müssen Sie mit Konstruktoren, die einen `culture`\-Parameter akzeptieren, neue Instanzen dieser Klassen initialisieren.  Geben Sie für den `culture`\-Parameter <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> an.  Im folgenden Codebeispiel wird der Konstruktor für eine kulturunabhängige `Hashtable` dargestellt.  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
## Verwenden der CollectionsUtil.CreateCaseInsensitiveHashTable\-Methode  
 Die `CollectionsUtil.CreateCaseInsensitiveHashTable`\-Methode eignet sich zum schnellen Erstellen einer neuen Instanz der `Hashtable`\-Klasse, bei der die Groß\-\/Kleinschreibung von Zeichenfolgen außer Acht gelassen wird.  Alle Überladungen der `CollectionsUtil.CreateCaseInsensitiveHashTable`\-Methode sind jedoch kulturabhängig, da sie die `Thread.CurrentCulture`\-Eigenschaft verwenden.  Mit dieser Methode kann keine kulturunabhängige `Hashtable` erstellt werden.  Um eine kulturunabhängige `Hashtable` zu erstellen, verwenden Sie den `Hashtable`\-Konstruktor, der einen `culture`\-Parameter akzeptiert.  Geben Sie für den `culture`\-Parameter `CultureInfo.InvariantCulture` an.  Im folgenden Codebeispiel wird der Konstruktor für eine kulturunabhängige `Hashtable` dargestellt.  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>   
## Verwenden der SortedList\-Klasse  
 Eine `SortedList` stellt eine Auflistung von Schlüssel\-Wert\-Paaren dar, die nach den Schlüsseln sortiert sind und auf die über Schlüssel und über Indizes zugegriffen werden kann.  Wenn Sie eine `SortedList` verwenden, bei der Zeichenfolgen als Schlüssel verwendet werden, können Sortier\- und Suchvorgänge durch die `Thread.CurrentCulture`\-Eigenschaft beeinflusst werden.  Um ein für eine `SortedList` kulturunabhängiges Verhalten zu erzielen, erstellen Sie die `SortedList` mit einem Konstruktor, der einen `comparer`\-Parameter akzeptiert.  Der `comparer`\-Parameter gibt die Implementierung von <xref:System.Collections.IComparer> an, die beim Vergleichen von Schlüsseln verwendet werden soll.  Geben Sie für den Parameter eine benutzerdefinierte Comparer\-Klasse an, die `CultureInfo.InvariantCulture` verwendet.  Das folgende Beispiel veranschaulicht eine benutzerdefinierte, kulturunabhängige Comparer\-Klasse, die Sie als `comparer`\-Parameter für einen `SortedList`\-Konstruktor angeben können.  
  
```vb  
Imports System  
Imports System.Collections  
Imports System.Globalization  
  
Friend Class InvariantComparer  
    Implements IComparer   
    Private m_compareInfo As CompareInfo  
    Friend Shared [Default] As New InvariantComparer()  
  
    Friend Sub New()  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo  
    End Sub     
  
    Public Function Compare(a As Object, b As Object) As Integer _  
            Implements IComparer.Compare  
        Dim sa As String = CType(a, String)  
        Dim sb As String = CType(b, String)  
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then  
            Return m_compareInfo.Compare(sa, sb)  
        Else  
            Return Comparer.Default.Compare(a, b)  
        End If  
    End Function  
End Class  
  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Globalization;  
  
internal class InvariantComparer : IComparer   
{  
    private CompareInfo m_compareInfo;  
    internal static readonly InvariantComparer Default = new  
        InvariantComparer();  
  
    internal InvariantComparer()   
    {  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;  
    }  
  
    public int Compare(Object a, Object b)  
    {  
        String sa = a as String;  
        String sb = b as String;  
        if (sa != null && sb != null)  
            return m_compareInfo.Compare(sa, sb);  
        else  
            return Comparer.Default.Compare(a,b);  
    }  
}  
```  
  
 Wenn Sie eine `SortedList` für Zeichenfolgen ohne Angabe eines benutzerdefinierten, invarianten Comparers verwenden, kann das Ändern von `Thread.CurrentCulture` nach dem Auffüllen der Liste dazu führen, dass die Liste ungültig wird.  
  
## Verwenden der ArrayList.Sort\-Methode  
 Überladungen der `ArrayList.Sort`\-Methode führen standardmäßig kulturabhängige Sortierungen mit der `Thread.CurrentCulture`\-Eigenschaft aus.  Die Ergebnisse können je nach Kultur aufgrund der unterschiedlichen Sortierreihenfolgen variieren.  Verwenden Sie zum Beenden des kulturabhängigen Verhaltens die Überladungen dieser Methode, die eine Implementierung von `IComparer` akzeptieren.  Geben Sie für den `comparer`\-Parameter eine benutzerdefinierte, invariante Comparer\-Klasse an, die `CultureInfo.InvariantCulture` verwendet.  Ein Beispiel für eine benutzerdefinierte, invariante Comparer\-Klasse finden Sie unter [Verwenden der SortedList\-Klasse](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).  
  
## Siehe auch  
 <xref:System.Collections.CaseInsensitiveComparer>   
 <xref:System.Collections.CaseInsensitiveHashCodeProvider>   
 <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName>   
 <xref:System.Collections.SortedList>   
 <xref:System.Collections.Hashtable>   
 <xref:System.Collections.IComparer>   
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)   
 [CollectionsUtil.CreateCaseInsensitiveHashTable\-Methode](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)