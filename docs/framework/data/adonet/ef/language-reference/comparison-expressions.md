---
title: "Vergleichsausdr&#252;cke | Microsoft Docs"
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
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vergleichsausdr&#252;cke
Ein Vergleichsausdruck überprüft, ob ein konstanter Wert, ein Eigenschaftswert oder das Ergebnis einer Methode gleich oder ungleich einem anderen Wert bzw. größer oder kleiner als ein anderer Wert ist.  Wenn ein bestimmter Vergleich für [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] nicht gültig ist, wird eine Ausnahme ausgelöst.  Für alle Vergleiche, sowohl implizite als auch explizite, ist es erforderlich, dass alle Komponenten in der Datenquelle vergleichbar sind.  Vergleichsausdrücke werden oft in `Where`\-Klauseln zur Einschränkung der Abfrageergebnisse verwendet.  
  
 Im folgenden Beispiel von Abfrageausdruckssyntax wird eine Abfrage dargestellt, die Ergebnisse mit der Auftragsnummer "SO43663" zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 Im folgenden Beispiel von methodenbasierter Abfragesyntax wird eine Abfrage dargestellt, die Ergebnisse mit der Auftragsnummer "SO43663" zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 Im folgenden Beispiel von Abfrageausdruckssyntax wird eine Abfrage dargestellt, die Auftragsinformationen zu Aufträgen mit dem Lieferdatum 8. Juli 2001 zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 Im folgenden Beispiel von methodenbasierter Abfragesyntax wird eine Abfrage dargestellt, die Auftragsinformationen zu Aufträgen mit dem Lieferdatum 8. Juli 2001 zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 Ausdrücke, die einen konstanten Wert zurückgeben, werden auf dem Server konvertiert, und es wird keine lokale Auswertung durchgeführt.  Im folgenden Beispiel wird ein Ausdruck in der `Where`\-Klausel verwendet, der eine Konstante zurückgibt.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] unterstützt die Verwendung von Benutzerklassen als Konstanten nicht.  Ein Eigenschaftsverweis in einer Benutzerklasse wird jedoch als konstant behandelt. Er wird in einen konstanten Ausdruck der Befehlsstruktur konvertiert und für die Datenquelle ausgeführt.  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 Methoden, die einen konstanten Ausdruck zurückgeben, werden nicht unterstützt.  Das folgende Beispiel enthält eine Methode in der `Where`\-Klausel, die eine Konstante zurückgibt.  Dieses Beispiel löst zur Laufzeit eine Ausnahme aus.  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## Siehe auch  
 [Ausdrücke in LINQ to Entities\-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)