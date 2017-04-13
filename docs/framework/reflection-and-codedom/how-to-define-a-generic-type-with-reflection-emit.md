---
title: "Gewusst wie: Definieren eines generischen Typs mit Reflektionsausgabe | Microsoft Docs"
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
  - "Generika [.NET Framework], Dynamische Typen"
  - "Generika [.NET Framework], Reflektionsausgabe"
  - "Reflektionsausgabe, Generische Typen"
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Definieren eines generischen Typs mit Reflektionsausgabe
In diesem Thema werden die folgenden Aufgaben erläutert: Erstellen eines einfachen generischen Typs mit zwei Typparametern, Anwenden von Klasseneinschränkungen, Schnittstelleneinschränkungen und besonderen Einschränkungen auf die Typparameter sowie Erstellen von Membern, die die Typparameter der Klasse als Parametertypen und Rückgabetypen verwenden.  
  
> [!IMPORTANT]
>  Eine Methode ist nicht generisch, weil sie zu einem generischen Typ gehört und die Typparameter dieses Typs verwendet.  Eine Methode ist nur dann generisch, wenn sie über eine eigene Typparameterliste verfügt.  Die meisten Methoden von generischen Typen sind nicht generisch, wie im vorliegenden Beispiel.  Ein Beispiel zum Ausgeben einer generischen Methode finden Sie unter [Gewusst wie: Definieren einer generischen Methode mit Reflektionsausgabe](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-method-with-reflection-emit.md).  
  
### So definieren Sie einen generischen Typ  
  
1.  Definieren Sie eine dynamische Assembly mit der Bezeichnung `GenericEmitExample1`.  In diesem Beispiel wird die Assembly ausgeführt und auf einem Datenträger gespeichert, daher wird <xref:System.Reflection.Emit.AssemblyBuilderAccess?displayProperty=fullName> angegeben.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2.  Definieren Sie ein dynamisches Modul.  Eine Assembly besteht aus ausführbaren Modulen.  Bei einer Assembly mit einem Modul entspricht der Modulname dem Assemblynamen, und der Dateiname besteht aus dem Modulnamen und einer Erweiterung.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3.  Definieren Sie eine Klasse.  In diesem Beispiel trägt die Klasse die Bezeichnung `Sample`.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4.  Definieren Sie die generischen Typparameter von `Sample`, indem Sie ein Array von Zeichenfolgen, das die Namen der Parameter enthält, an die <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=fullName>\-Methode übergeben.  Dies macht die Klasse zu einem generischen Typ.  Der Rückgabewert ist ein Array von <xref:System.Reflection.Emit.GenericTypeParameterBuilder>\-Objekten, die die Typparameter darstellen, die im ausgegebenen Code verwendet werden können.  
  
     Im folgenden Code wird `Sample` in einen generischen Typ mit den beiden Typparametern `TFirst` und `TSecond` umgewandelt.  Um den Code verständlicher zu gestalten, wird jeder <xref:System.Reflection.Emit.GenericTypeParameterBuilder> in eine Variable mit dem gleichen Namen wie der Typparameter aufgenommen.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5.  Fügen Sie den Typparametern besondere Einschränkungen hinzu.  In diesem Beispiel wird der Typparameter `TFirst` auf Typen mit parameterlosen Konstruktoren und auf Verweistypen eingeschränkt.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6.  Fügen Sie den Typparametern bei Bedarf Klassen\- und Schnittstelleneinschränkungen hinzu.  In diesem Beispiel wird der Typparameter `TFirst` auf Typen eingeschränkt, die von der Basisklasse abgeleitet sind, die von dem in der Variable `baseType` enthaltenen <xref:System.Type>\-Objekt dargestellt wird, und die die Schnittstellen implementieren, deren Typen sich in den Variablen `interfaceA` und `interfaceB` befinden.  Die Deklaration und die Zuweisung dieser Variablen können Sie dem Codebeispiel entnehmen.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7.  Definieren Sie ein Feld.  In diesem Beispiel wird der Typ des Felds vom Typparameter `TFirst` angegeben.  <xref:System.Reflection.Emit.GenericTypeParameterBuilder> wird von <xref:System.Type> abgeleitet, sodass Sie generische Typparameter überall dort verwenden können, wo ein Typ verwendet werden kann.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8.  Definieren Sie eine Methode, die die Typparameter des generischen Typs verwendet.  Beachten Sie, dass solche Methoden nur dann generisch sind, wenn sie über eigene Typparameterlisten verfügen.  Im folgenden Code wird eine `static`\-Methode \(`Shared` in Visual Basic\) definiert, die ein Array von `TFirst` akzeptiert und ein `List<TFirst>` \(`List(Of TFirst)` in Visual Basic\) zurückgibt, das sämtliche Elemente des Arrays enthält.  Für die Definition dieser Methode muss der Typ `List<TFirst>` erstellt werden, indem <xref:System.Type.MakeGenericType%2A> für die Definition eines generischen Typs `List<T>` aufgerufen wird. \(Wenn Sie den Operator `typeof` \(`GetType` in Visual Basic\) zum Abrufen der Definition eines generischen Typs verwenden, wird das `T` ausgelassen.\) Der Parametertyp wird mithilfe der <xref:System.Type.MakeArrayType%2A>\-Methode erstellt.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. Geben Sie den Methodentext aus.  Der Methodentext besteht aus drei Opcodes, die das Eingabearray auf den Stapel laden, den `List<TFirst>`\-Konstruktor aufrufen, der `IEnumerable<TFirst>` annimmt \(der die Eingabeelemente in die Liste einfügt\) und die Methode beenden \(wobei das neue <xref:System.Collections.Generic.List%601>\-Objekt auf dem Stapel verbleibt\).  Der Schwierigkeit beim Ausgeben des Codes liegt im Abrufen des Konstruktors.  
  
     Da die <xref:System.Type.GetConstructor%2A>\-Methode bei einem <xref:System.Reflection.Emit.GenericTypeParameterBuilder> nicht unterstützt wird, kann der Konstruktor von `List<TFirst>` nicht direkt abgerufen werden.  Zunächst muss der Konstruktor der Definition des generischen Typs `List<T>` abgerufen und dann eine Methode aufgerufen werden, die diesen in den entsprechenden Konstruktor von `List<TFirst>` konvertiert.  
  
     Der in diesem Codebeispiel verwendete Konstruktor nimmt ein `IEnumerable<T>` an.  Beachten Sie jedoch, dass es sich dabei nicht um die Definition des generischen Typs der generischen <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle handelt. Der Typparameter `T` von `List<T>` muss vielmehr durch den Typparameter `T` von `IEnumerable<T>` ersetzt werden. \(Dies verwirrt auf den ersten Blick, da beide Typen über Typparameter mit der Bezeichnung `T` verfügen.  Daher werden in diesem Codebeispiel die Bezeichnungen `TFirst` und `TSecond` verwendet.\) Um den Typ des Konstruktorarguments abzurufen, beginnen Sie mit der Definition des generischen Typs `IEnumerable<T>`, und rufen Sie <xref:System.Type.MakeGenericType%2A> mit dem ersten generischen Typparameter von `List<T>` auf.  Die Konstruktorargumentliste muss als Array übergeben werden, in diesem Fall mit nur einem Argument.  
  
    > [!NOTE]
    >  Die Definition des generischen Typs wird als `IEnumerable<>` ausgedrückt, wenn Sie den Operator `typeof` in C\# verwenden, oder als `IEnumerable(Of )`, wenn Sie den Operator `GetType` in Visual Basic verwenden.  
  
     Der Konstruktor von `List<T>` kann jetzt durch Aufrufen von <xref:System.Type.GetConstructor%2A> für die Definition des generischen Typs aufgerufen werden.  Um diesen Konstruktor in den entsprechenden Konstruktor von `List<TFirst>` zu konvertieren, übergeben Sie `List<TFirst>` und den Konstruktor von `List<T>` an die statische <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=fullName>\-Methode.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. Erstellen Sie den Typ, und speichern Sie die Datei.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. Rufen Sie die Methode auf.  Die `ExampleMethod` ist nicht generisch, sie gehört jedoch einem generischen Typ an. Zum Abrufen einer <xref:System.Reflection.MethodInfo>, die aufgerufen werden kann, muss ein konstruierter Typ aus der Typdefinition für `Sample` erstellt werden.  Der konstruierte Typ verwendet die `Example`\-Klasse, die die Einschränkungen für `TFirst` erfüllt, da es sich um einen Verweistyp mit einem standardmäßig parameterlosen Konstruktor handelt, und die `ExampleDerived`\-Klasse, die die Einschränkungen für `TSecond` erfüllt. \(Den Code für `ExampleDerived` finden Sie im Beispielcodeabschnitt.\) Diese beiden Typen werden zur Erstellung des konstruierten Typs an <xref:System.Type.MakeGenericType%2A> übergeben.  Anschließend wird die <xref:System.Reflection.MethodInfo> mithilfe der <xref:System.Type.GetMethod%2A>\-Methode abgerufen.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. Im folgenden Code wird ein Array von `Example`\-Objekten erstellt. Dieses wird in ein Array vom Typ <xref:System.Object> eingefügt, das die Argumente der aufzurufenden Methode darstellt, und an die [Invoke\(Object, Object\<xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29>\-Methode übergeben.  Das erste Argument der <xref:System.Reflection.MethodBase.Invoke%2A>\-Methode ist ein NULL\-Verweis, da die Methode `static` ist.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## Beispiel  
 Im folgenden Codebeispiel werden neben einer Klasse mit der Bezeichnung `Sample` eine Basisklasse und zwei Schnittstellen definiert.  Das Programm definiert zwei generische Typparameter für `Sample` und wandelt es in einen generischen Typ um.  Ein Typ wird einzig und allein durch Typparameter zu einem generischen Typ.  Im Programm wird dies anhand einer Testmeldung angegeben, die vor und nach der Definition der Typparameter angezeigt wird.  
  
 Mit dem Typparameter `TSecond` werden anhand der Basisklasse und Schnittstellen die Klassen\- und Schnittstelleneinschränkungen dargestellt, und mit dem Typparameter `TFirst` werden besondere Einschränkungen dargestellt.  
  
 Im Codebeispiel werden ein Feld und eine Methode definiert, wobei die Typparameter der Klasse für den Feldtyp und für den Parameter\- und Rückgabetyp der Methode verwendet werden.  
  
 Nach dem Erstellen der `Sample`\-Klasse wird die Methode aufgerufen.  
  
 Das Programm enthält eine Methode, die Informationen über einen generischen Typ auflistet, und eine Methode, die besondere Einschränkungen für einen Typparameter auflistet.  Mit diesen Methoden werden Informationen über die fertig gestellte `Sample`\-Klasse angezeigt.  
  
 Das Programm speichert das fertig gestellte Modul als `GenericEmitExample1.dll` auf dem Datenträger, sodass Sie es mit dem [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) öffnen und den MSIL\-Code für die `Sample`\-Klasse untersuchen können.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## Kompilieren des Codes  
  
-   Der Code enthält die für die Kompilierung erforderlichen `using`\-Anweisungen für C\# \(`Imports` in Visual Basic\).  
  
-   Er werden keine weiteren Assemblyverweise benötigt.  
  
-   Kompilieren Sie den Code über die Befehlszeile mit csc.exe, vbc.exe oder cl.exe.  Um den Code in Visual Studio zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## Siehe auch  
 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>   
 [Using Reflection Emit](http://msdn.microsoft.com/de-de/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Reflection Emit Dynamic Assembly Scenarios](http://msdn.microsoft.com/de-de/e1cc6750-e20f-473b-bb4e-f43bc66aecce)