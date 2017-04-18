---
title: Reflektion (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ae042933575849e105d7b681634a61319c1d6ee
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-visual-basic"></a>Reflektion (Visual Basic)
Reflektion stellt Objekte (des Typs <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</xref:System.Type> Sie können mithilfe von Reflektion dynamisch eine Instanz eines Typs erstellen, Typen an ein vorhandenes Objekt binden oder Typinformationen von vorhandenen Objekten und Aufrufen ihrer Methoden oder dessen Felder und Eigenschaften zugreifen. Wenn Sie Attribute in Ihrem Code verwenden, können Sie Reflektion, darauf zuzugreifen. Weitere Informationen finden Sie unter [Attribute](https://msdn.microsoft.com/library/5x6cd29c).  
  
 Hier ist ein einfaches Beispiel veranschaulicht die Verwendung der statischen Methode `GetType` - geerbten alle Typen aus der `Object` -Basisklasse - zum Abrufen des Typs einer Variablen:  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 Die Ausgabe lautet:  
  
 `System.Int32`  
  
 Das folgende Beispiel verwendet Reflektion, um den vollständigen Namen der geladenen Assembly abzurufen.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 Die Ausgabe lautet:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Übersicht über Reflektion  
 Reflektion ist in folgenden Situationen nützlich:  
  
-   Wenn Sie Attribute in den Metadaten des Programms zugreifen müssen. Weitere Informationen finden Sie unter [Abrufen von Informationen, die in Attributen gespeicherte](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).  
  
-   Zum Untersuchen und Instanziieren von Typen in einer Assembly.  
  
-   Zum Erstellen neuer Typen zur Laufzeit. Verwenden Sie die Klassen in <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit>  
  
-   Zum Ausführen von späten Bindung, die Zugriff auf Methoden in Typen, die zur Laufzeit erstellt. Finden Sie unter [dynamisches Laden und Verwenden von Typen](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:   
  
-   [Reflektion](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [Anzeigen von Typinformationen](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [Reflektion und generische Typen](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <xref:System.Reflection.Emit></xref:System.Reflection.Emit>  
  
-   [Abrufen von Informationen aus Attributen](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)   
 [Assemblys in der Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)
