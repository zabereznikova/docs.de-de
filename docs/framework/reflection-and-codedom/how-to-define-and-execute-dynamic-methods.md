---
title: "Gewusst wie: Definieren und Ausf&#252;hren von dynamischen Methoden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dynamische Methoden"
  - "Reflektionsausgabe, Dynamische Methoden"
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Definieren und Ausf&#252;hren von dynamischen Methoden
In den folgenden Verfahren wird beschrieben, wie eine einfache dynamische Methode und eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, definiert und ausgeführt werden.  Weitere Informationen über dynamische Methoden finden Sie unter der <xref:System.Reflection.Emit.DynamicMethod>\-Klasse und unter [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/de-de/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e).  
  
### So definieren Sie eine dynamische Methode und führen diese aus  
  
1.  Deklarieren Sie einen Delegattyp, um die Methode auszuführen.  Es empfiehlt sich, einen generischen Delegaten zu verwenden, um die Anzahl der zu deklarierenden Delegattypen möglichst gering zu halten.  Im folgenden Code werden zwei Delegattypen \(einer davon generisch\) deklariert, die für die `SquareIt`\-Methode verwendet werden können.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2.  Erstellen Sie ein Array, das die Parametertypen für die dynamische Methode angibt.  Der einzige Parameter in diesem Beispiel ist ein `int` \(`Integer` in Visual Basic\), sodass das Array nur ein Element enthält.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3.  Erstellen Sie eine <xref:System.Reflection.Emit.DynamicMethod>.  In diesem Beispiel trägt die Methode die Bezeichnung `SquareIt`.  
  
    > [!NOTE]
    >  Dynamische Methoden müssen nicht bezeichnet werden, denn sie können nicht anhand des Namens aufgerufen werden.  Mehrere dynamische Methoden können den gleichen Namen haben.  Der Name wird jedoch in Aufruflisten angezeigt und kann für Debuggen nützlich sein.  
  
     Der Typ des Rückgabewerts wird als `long` angegeben.  Die Methode ist dem Modul zugeordnet, das die `Example`\-Klasse mit dem Beispielcode enthält.  Es kann jedes geladene Modul angegeben werden.  Die dynamischen Methoden funktionieren wie eine `static`\-Methode \(`Shared` in Visual Basic\) auf Modulebene.  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4.  Geben Sie den Methodentext aus.  In diesem Beispiel wird ein <xref:System.Reflection.Emit.ILGenerator>\-Objekt verwendet, um die Microsoft Intermediate Language \(MSIL\) auszugeben.  Der Methodentext einer <xref:System.Reflection.Emit.DynamicMethod> kann jedoch auch über ein <xref:System.Reflection.Emit.DynamicILInfo>\-Objekt in Verbindung mit nicht verwalteten Code\-Generatoren ausgegeben werden.  
  
     Der MSIL\-Code in diesem Beispiel lädt das Argument, bei dem es sich um ein `int` handelt, auf den Stapel, konvertiert es in ein `long`, dupliziert das `long` und multipliziert die beiden Zahlen.  Somit verbleibt das quadrierte Ergebnis auf dem Stapel, und die Methode kann beendet werden.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5.  Erstellen Sie eine Instanz des in Schritt 1 deklarierten Delegaten, der die dynamische Methode durch Aufrufen der <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>\-Methode darstellt.  Mit der Erstellung des Delegaten ist die Methode abgeschlossen. Alle Versuche, die Methode zu ändern, z. B. durch Hinzufügen von weiterem MSIL\-Code, werden ignoriert.  Im folgenden Code wird der Delegat erstellt und mithilfe eines generischen Delegaten aufgerufen.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### So definieren Sie eine dynamische Methode, die an ein Objekt gebunden ist, und führen diese aus  
  
1.  Deklarieren Sie einen Delegattyp, um die Methode auszuführen.  Es empfiehlt sich, einen generischen Delegaten zu verwenden, um die Anzahl der zu deklarierenden Delegattypen möglichst gering zu halten.  Im folgenden Code wird ein generischer Delegattyp deklariert, mit dem alle Methoden, die über einen Parameter und einen Rückgabewert oder, sofern der Delegat an ein Objekt gebunden ist, über zwei Parameter und einen Rückgabewert verfügen, ausgeführt werden können.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2.  Erstellen Sie ein Array, das die Parametertypen für die dynamische Methode angibt.  Wenn der Delegat, der die Methode darstellt, an ein Objekt gebunden werden soll, muss der erste Parameter dem Typ entsprechen, an den der Delegat gebunden wird.  In diesem Beispiel gibt es zwei Parameter, vom Typ `Example` und Typ `int` \(`Integer` in Visual Basic\).  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3.  Erstellen Sie eine <xref:System.Reflection.Emit.DynamicMethod>.  In diesem Beispiel verfügt die Methode über keinen Namen.  Der Typ des Rückgabewerts wird als `int` \(`Integer` in Visual Basic\) angegeben.  Die Methode kann auf private und geschützte Member der `Example`\-Klasse zugreifen.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4.  Geben Sie den Methodentext aus.  In diesem Beispiel wird ein <xref:System.Reflection.Emit.ILGenerator>\-Objekt verwendet, um die Microsoft Intermediate Language \(MSIL\) auszugeben.  Der Methodentext einer <xref:System.Reflection.Emit.DynamicMethod> kann jedoch auch über ein <xref:System.Reflection.Emit.DynamicILInfo>\-Objekt in Verbindung mit nicht verwalteten Code\-Generatoren ausgegeben werden.  
  
     Der MSIL\-Code in diesem Beispiel lädt das erste Argument, bei dem es sich um eine Instanz der `Example`\-Klasse handelt, und lädt mit dieser den Wert eines privaten Instanzfeldes vom Typ `int`.  Das zweite Argument wird geladen, und die beiden Zahlen werden multipliziert.  Wenn das Ergebnis größer als `int` ist, wird der Wert abgeschnitten, und die wichtigsten Bits werden verworfen.  Die Methode wird beendet, wobei der Rückgabewert auf dem Stapel abgelegt wird.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5.  Erstellen Sie eine Instanz des in Schritt 1 deklarierten Delegaten, der die dynamische Methode durch Aufrufen der <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29>\-Methodenüberladung darstellt.  Mit der Erstellung des Delegaten ist die Methode abgeschlossen. Alle Versuche, die Methode zu ändern, z. B. durch Hinzufügen von weiterem MSIL\-Code, werden ignoriert.  
  
    > [!NOTE]
    >  Die <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>\-Methode kann mehrfach aufgerufen werden, um Delegaten zu erstellen, die an andere Instanzen des Zieltyps gebunden sind.  
  
     Im folgenden Code wird die Methode an eine neue Instanz der `Example`\-Klasse gebunden, deren privates Testfeld auf 42 festgelegt ist.  Auf diese Weise wird bei jedem Aufruf des Delegaten die Instanz von `Example` an den ersten Parameter der Methode übergeben.  
  
     Der Delegat `OneParameter` wird verwendet, da der erste Parameter der Methode immer die Instanz von `Example` erhält.  Wenn der Delegat aufgerufen wird, ist nur der zweite Parameter erforderlich.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## Beispiel  
 Im folgenden Codebeispiel werden eine einfache dynamische Methode und eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, veranschaulicht.  
  
 Die einfache dynamische Methode nimmt ein Argument an, einen 32\-Bit\-Ganzzahl, und gibt die das 64\-Bit\-Quadrat dieser Ganzzahl zurück.  Die Methode wird mithilfe eines generischen Delegaten aufgerufen.  
  
 Die zweite dynamische Methode verfügt über zwei Parameter, vom Typ `Example` und vom Typ `int` \(`Integer` in Visual Basic\).  Nach der Erstellung wird die dynamische Methode an eine Instanz von `Example` gebunden. Dafür wird ein generischer Delegat mit einem Argument vom Typ `int` verwendet.  Der Delegat verfügt über kein Argument vom Typ `Example`, da der erste Parameter der Methode immer die gebundene Instanz von `Example` erhält.  Wenn der Delegat aufgerufen wird, wird nur das `int`\-Argument angegeben.  Diese dynamische Methode greift auf ein privates Feld der `Example`\-Klasse zu und gibt das Produkt des privaten Feldes und des `int`\-Arguments zurück.  
  
 Im Codebeispiel werden Delegaten definiert, die zum Ausführen der Methoden verwendet werden können.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## Kompilieren des Codes  
  
-   Der Code enthält die für die Kompilierung erforderlichen `using`\-Anweisungen für C\# \(`Imports` in Visual Basic\).  
  
-   Er werden keine weiteren Assemblyverweise benötigt.  
  
-   Kompilieren Sie den Code über die Befehlszeile mit csc.exe, vbc.exe oder cl.exe.  Um den Code in Visual Studio zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## Siehe auch  
 <xref:System.Reflection.Emit.DynamicMethod>   
 [Using Reflection Emit](http://msdn.microsoft.com/de-de/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/de-de/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)