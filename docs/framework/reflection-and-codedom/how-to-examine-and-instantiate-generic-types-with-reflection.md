---
title: "Gewusst wie: Untersuchen und Instanziieren von generischen Typen mit Reflektion | Microsoft Docs"
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
  - "Generika [.NET Framework], Reflektion"
  - "Reflektion, Generische Typen"
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Untersuchen und Instanziieren von generischen Typen mit Reflektion
Die Informationen über generische Typen werden, genau wie Informationen über andere Typen, durch Untersuchen eines <xref:System.Type>\-Objekts abgerufen, dass den generischen Typ darstellt.  Der grundsätzliche Unterschied liegt darin, dass ein generischer Typ über eine Liste von <xref:System.Type>\-Objekten verfügt, die seine generischen Typparameter darstellen.  Die erste Prozedur in diesem Abschnitt untersucht generische Typen.  
  
 Sie können ein <xref:System.Type>\-Objekt erstellen, das einen konstruierten Typ darstellt, indem Sie Typargumente an die Typparameter einer Definition eines generischen Typs binden.  Dies wird in der zweiten Prozedur veranschaulicht.  
  
### So untersuchen Sie einen generischen Typ und seine Typparameter  
  
1.  Rufen Sie eine Instanz von <xref:System.Type> ab, die den generischen Typ darstellt.  Im folgenden Code wird der Typ mit dem Operator `typeof` in C\# \(`GetType` in Visual Basic, `typeid` in Visual C\+\+\) abgerufen.  Andere Möglichkeiten zum Abrufen eines <xref:System.Type>\-Objekts finden Sie im Thema über die <xref:System.Type>\-Klasse.  Beachten Sie, dass sich der Typ im Rest der Prozedur in einem Methodenparameter mit der Bezeichnung `t` befindet.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2.  Ermitteln Sie über die <xref:System.Type.IsGenericType%2A>\-Eigenschaft, ob es sich um einen generischen Typ handelt, und über die <xref:System.Type.IsGenericTypeDefinition%2A>\-Eigenschaft, ob es sich bei dem Typ um eine Definition eines generischen Typs handelt.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3.  Rufen Sie mithilfe der <xref:System.Type.GetGenericArguments%2A>\-Methode ein Array ab, das die generischen Typargumente enthält.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4.  Bestimmen Sie anhand der <xref:System.Type.IsGenericParameter%2A>\-Eigenschaft für jedes Typargument, ob es sich um einen Typparameter \(z. B. in einer Definition eines generischen Typs\) oder um einen Typ handelt, der für einen Typparameter angegeben wurde \(z. B. in einem konstruierten Typ\).  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5.  Ein generischer Typparameter wird innerhalb des Typsystems, genau wie ein normaler Typ, durch eine Instanz von <xref:System.Type> dargestellt.  Im folgenden Code werden der Name und die Parameterposition eines <xref:System.Type>\-Objekts angezeigt, das einen generischen Typparameter darstellt.  Die Parameterposition hat in diesem Fall keine Bedeutung. Sie kann aber z. B. von Interesse sein, wenn Sie einen Typparameter untersuchen, der von einem anderen generischen Typ als Typargument verwendet wurde.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6.  Ermitteln Sie die Basistypeinschränkung und die Schnittstelleneinschränkungen eines generischen Typparameters mithilfe der <xref:System.Type.GetGenericParameterConstraints%2A>\-Methode, um sämtliche Einschränkungen in einem einzelnen Array abzurufen.  Die Einschränkungen werden nicht unbedingt in einer bestimmten Reihenfolge angezeigt.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7.  Mit der <xref:System.Type.GenericParameterAttributes%2A>\-Eigenschaft können Sie die besonderen Einschränkungen für einen Typparameter erkennen, z. B., dass dieser ein Verweistyp sein muss.  Die Eigenschaft enthält auch Werte, die Varianz darstellen, die Sie, wie im folgenden Code dargestellt, maskieren können.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8.  Die Attribute für besondere Einschränkungen sind Flags, und das Flag \(<xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName>\), das bedeutet, dass keine besonderen Einschränkungen vorliegen, bedeutet auch, dass keine Kovarianz oder Kontravarianz vorhanden ist.  Um zu überprüfen, ob eine dieser Bedingungen zutrifft, müssen Sie daher die entsprechende Maske verwenden.  Verwenden Sie in diesem Fall <xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName>, um die Flags für besondere Einschränkungen zu isolieren.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## Erstellen einer Instanz eines generischen Typs  
 Ein generischer Typ ist im Prinzip eine Vorlage.  Sie können keine Instanzen aus diesem erstellen, es sei denn, Sie geben für seine generischen Typparameter echte Typen an.  Um dieses zur Laufzeit mit Reflektion durchzuführen, müssen Sie die <xref:System.Type.MakeGenericType%2A>\-Methode verwenden.  
  
#### So erstellen Sie eine Instanz eines generischen Typs  
  
1.  Rufen Sie ein <xref:System.Type>\-Objekt ab, das den generischen Typ darstellt.  Im folgenden Code wird der generische Typ <xref:System.Collections.Generic.Dictionary%602> auf zwei Arten abgerufen: anhand der <xref:System.Type.GetType%28System.String%29?displayProperty=fullName>\-Methodenüberladung mit einer Zeichenfolge, die den Typ beschreibt, und durch Aufrufen der <xref:System.Type.GetGenericTypeDefinition%2A>\-Methode für den konstruierten Typ `Dictionary\<String, Example>` \(`Dictionary(Of String, Example)` in Visual Basic\).  Für die <xref:System.Type.MakeGenericType%2A>\-Methode ist eine Definition eines generischen Typs erforderlich.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2.  Erstellen Sie ein Array von Typargumenten, die die Typparameter ersetzen sollen.  Das Array muss die richtige Anzahl von <xref:System.Type>\-Objekten in der Reihenfolge enthalten, in der sie in der Typparameterliste aufgeführt sind.  In diesem Fall ist der Schlüssel \(der erste Typparameter\) vom Typ <xref:System.String>, und die Werte im Wörterbuch sind Instanzen einer Klasse mit der Bezeichnung `Example`.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3.  Rufen Sie die <xref:System.Type.MakeGenericType%2A>\-Methode auf, um die Typargumente an die Typparameter zu binden und den Typ zu erstellen.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4.  Erstellen Sie mithilfe der <xref:System.Activator.CreateInstance%28System.Type%29>\-Methodenüberladung ein Objekt des konstruierten Typs.  Im folgenden Code werden zwei Instanzen der `Example`\-Klasse im resultierenden `Dictionary<String, Example>`\-Objekt gespeichert.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine `DisplayGenericType`\-Methode definiert, mit der die im Code verwendeten Definitionen des generischen Typs und konstruierte Typen untersucht und die entsprechenden Informationen angezeigt werden.  Die `DisplayGenericType`\-Methode zeigt, wie die Eigenschaften <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> und <xref:System.Type.GenericParameterPosition%2A> sowie die <xref:System.Type.GetGenericArguments%2A>\-Methode verwendet werden.  
  
 Weiterhin wird im Beispiel eine `DisplayGenericParameter`\-Methode definiert, mit der ein generischer Typparameter untersucht und seine Einschränkungen angezeigt werden sollen.  
  
 Im Codebeispiel wird eine Gruppe von Testtypen definiert, u. a. ein generischer Typ, der die Einschränkungen der Typparameter veranschaulicht und zeigt, wie Informationen über diese Typen angezeigt werden können.  
  
 Es wird ein Typ aus der <xref:System.Collections.Generic.Dictionary%602>\-Klasse konstruiert, indem ein Array von Typparametern erstellt und die <xref:System.Type.MakeGenericType%2A>\-Methode aufgerufen wird.  Das Programm vergleicht das mit <xref:System.Type.MakeGenericType%2A> erstellte <xref:System.Type>\-Objekt mit einem <xref:System.Type>\-Objekt, das über `typeof` \(`GetType` in Visual Basic\) abgerufen wurde, um zu verdeutlichen, dass sie gleich sind.  Entsprechend muss das Programm die Definition des generischen Typs für den konstruierten Typ mithilfe der <xref:System.Type.GetGenericTypeDefinition%2A>\-Methode abrufen und diese mit dem <xref:System.Type>\-Objekt vergleichen, das die <xref:System.Collections.Generic.Dictionary%602>\-Klasse darstellt.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## Kompilieren des Codes  
  
-   Der Code enthält die für die Kompilierung erforderlichen `using`\-Anweisungen für C\# \(`Imports` in Visual Basic\).  
  
-   Er werden keine weiteren Assemblyverweise benötigt.  
  
-   Kompilieren Sie den Code über die Befehlszeile mit csc.exe, vbc.exe oder cl.exe.  Um den Code in Visual Studio zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## Siehe auch  
 <xref:System.Type>   
 <xref:System.Reflection.MethodInfo>   
 [Reflektion und generische Typen](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)   
 [Anzeigen von Typinformationen](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Generika](../../../docs/standard/generics/index.md)