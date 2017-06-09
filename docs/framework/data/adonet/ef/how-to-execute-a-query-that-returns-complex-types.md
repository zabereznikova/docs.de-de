---
title: "Gewusst wie: Ausf&#252;hren einer Abfrage, die komplexe Typen zur&#252;ckgibt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Ausf&#252;hren einer Abfrage, die komplexe Typen zur&#252;ckgibt
Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfrage ausgeführt wird, die Entitätstypobjekte zurückgibt, die eine Eigenschaft eines komplexen Typs enthalten.  
  
### So führen Sie den Code in diesem Beispiel aus  
  
1.  Fügen Sie dem Projekt das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) hinzu, und konfigurieren Sie das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Doppelklicken Sie auf die EDMX\-Datei, um das Modell im [Modellbrowser\-Fenster](http://msdn.microsoft.com/de-de/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) des Entity Designers anzuzeigen.  Wählen Sie auf der Entity Designer\-Oberfläche die Eigenschaften `Email` und `Phone` des Entitätstyps `Contact` aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **In neuen komplexen Typ umgestalten** aus.  
  
4.  Ein neuer komplexer Typ mit den ausgewählten Eigenschaften `Email` und `Phone` wird dem **Modellbrowser** hinzugefügt.  Dem komplexen Typ wurde ein Standardname zugewiesen. Benennen Sie den Typ im **Eigenschaftenfenster** in `EmailPhone` um.  Außerdem wurde dem Entitätstyp `Contact` die Eigenschaft `ComplexProperty` hinzugefügt.  Geben Sie der Eigenschaft den Namen `EmailPhoneComplexType.`  
  
     Informationen zum Erstellen und Ändern von komplexen Typen mit dem Assistenten für Entity Data Model finden Sie unter [How to: Refactor Existing Properties into a Complex Type Property](http://msdn.microsoft.com/de-de/5b2eb3b3-693d-42cb-b43a-405812d677eb) und[How to: Create and Modify Complex Types](http://msdn.microsoft.com/de-de/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Abfrage gezeigt, die eine Auflistung von `Contact`\-Objekten zurückgibt und zwei Eigenschaften des `Contact` \-Objekts anzeigt: `ContactID` und die Werte des komplexen Typs `EmailPhoneComplexType`.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]