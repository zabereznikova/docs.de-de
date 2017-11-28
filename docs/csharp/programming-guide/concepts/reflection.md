---
title: Reflektion (C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f567eb47d93fcd95e5895b4b44e1c89fb0b901b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reflection-c"></a>Reflektion (C#)
Reflektion bietet Objekte (vom Typ <xref:System.Type>), die Assemblys, Module und Typen beschreiben. Mithilfe von Reflektion können Sie dynamisch eine Instanz eines Typs erzeugen, den Typ an ein vorhandenes Objekt binden und Typinformationen von vorhandenen Objekten abfragen. Ebenso wird erläutert wie die Methoden vorhandener Objekte aufgerufen und auf ihre Felder und Eigenschaften zugegriffen werden kann. Wenn Sie Attribute in Ihrem Code verwenden, können Sie mit Reflektion auf diese zugreifen. Weitere Informationen finden Sie unter [Attribute](https://msdn.microsoft.com/library/5x6cd29c).  
  
 Hier sehen Sie ein einfaches Beispiel für Reflektion mit der statischen Methode `GetType`, die von allen Typen der Basisklasse `Object` geerbt wird, zum Abrufen von Typinformationen einer Variable:  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 Ausgabe:  
  
 `System.Int32`  
  
 Im folgenden Beispiel wird Reflektion verwendet, um den vollständigen Namen der geladenen Assembly abzurufen.  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 Ausgabe:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  Die C#-Schlüsselwörter `protected` und `internal` haben in IL keine Bedeutung und werden nicht in Reflektions-APIs verwendet. Die entsprechenden Begriffe in IL sind *Family* und *Assembly*. Verwenden Sie zum Identifizieren einer `internal`-Methode mithilfe von Reflektion die Eigenschaft <xref:System.Reflection.MethodBase.IsAssembly%2A>. Verwenden Sie <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> zum Identifizieren einer Methode `protected internal`.  
  
## <a name="reflection-overview"></a>Übersicht über Reflektion  
 Reflektion ist in folgenden Situationen nützlich:  
  
-   Wenn Sie in den Metadaten Ihres Programms auf Attribute zugreifen müssen Weitere Informationen finden Sie unter [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md).  
  
-   Zum Untersuchen und Instanziieren von Typen in einer Assembly  
  
-   Zum Erstellen neuer Typen zur Laufzeit Verwenden Sie Klassen in <xref:System.Reflection.Emit>.  
  
-   Zum Ausführen von spätem Binden mit Zugriff auf Methoden der zur Laufzeit erstellten Typen Weitere Informationen finden Sie im Thema [Dynamisches Laden und Verwenden von Typen](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:   
  
-   [Reflektion](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [Anzeigen von Typinformationen](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [Reflektion und generische Typen](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Assemblys in der Common Language Runtime (CLR)](https://msdn.microsoft.com/library/k3677y81)
