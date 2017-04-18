---
title: Warten von Name-Wert-Paaren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 54db297ecd39e37492dcf8bb4de4f64476662670
ms.lasthandoff: 03/13/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a>Verwalten von Name/Wert-Paaren (Visual Basic)
Viele Anwendungen müssen Informationen verwalten, die am besten als Name/Wert-Paare geführt werden. Solche Informationen können z. B. Konfigurationsinformationen oder globale Einstellungen sein. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] enthält einige Methoden, die das Unterhalten von Name/Wert-Paaren vereinfachen. Sie können die Informationen entweder als Attribute oder als Satz untergeordneter Elemente unterhalten.  
  
 Ein Unterschied zwischen diesen beiden Formen besteht darin, dass Attribute der Beschränkung unterliegen, dass pro Element immer nur ein Attribut mit einem bestimmten Namen vorhanden sein darf. Für untergeordnete Elemente gilt diese Einschränkung nicht.  
  
## <a name="setattributevalue-and-setelementvalue"></a>"SetAttributeValue" und "SetElementValue"  
 Die zwei Methoden, vereinfachen Name/Wert-Paare sind <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>und <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A> Diese beiden Methoden besitzen eine ähnliche Semantik.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>können hinzufügen, ändern oder Entfernen von Attributen eines Elements.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>mit einem Namen eines Attributs, das nicht vorhanden ist, die Methode erstellt ein neues Attribut und fügt es in das angegebene Element hinzu.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>mit einem Namen eines vorhandenen Attributs und einem angegebenen Inhalt aus, der Inhalt des Attributs ersetzt durch den angegebenen Inhalt.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>mit einem Namen eines vorhandenen Attribut, und geben Sie null für den Inhalt das Attribut aus dem übergeordneten Element entfernt.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>können hinzufügen, ändern oder entfernen die untergeordneten Elemente eines Elements.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetElementValue%2A>mit einem Namen eines untergeordneten Elements, das nicht vorhanden ist, die Methode erstellt ein neues Element und fügt es in das angegebene Element hinzu.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetElementValue%2A>mit einem Namen eines vorhandenen Elements und einem angegebenen Inhalt, den Inhalt des Elements ersetzt durch den angegebenen Inhalt.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetElementValue%2A>mit einem Namen eines vorhandenen Elements, und geben Sie null für den Inhalt, wird das Element aus dem übergeordneten Element entfernt.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Element, das keine Attribute besitzt. Anschließend wird mithilfe der <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>-Methode zum Erstellen und verwalten Sie eine Liste von Name/Wert-Paaren.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Element, das keine untergeordneten Elemente besitzt. Anschließend wird mithilfe der <xref:System.Xml.Linq.XElement.SetElementValue%2A>-Methode zum Erstellen und verwalten Sie eine Liste von Name/Wert-Paaren.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A>   
 <xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A>   
 [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
