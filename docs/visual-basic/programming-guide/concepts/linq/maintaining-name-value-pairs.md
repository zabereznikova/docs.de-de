---
title: Warten von Name-Wert-Paaren
ms.date: 07/20/2015
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
ms.openlocfilehash: ed9c7f0aae2fe646cd723321f45455f89dd7c370
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331661"
---
# <a name="maintaining-namevalue-pairs-visual-basic"></a>Warten von Name-Wert-Paaren (Visual Basic)
Viele Anwendungen müssen Informationen verwalten, die am besten als Name/Wert-Paare geführt werden. Solche Informationen können z. B. Konfigurationsinformationen oder globale Einstellungen sein. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enthält einige Methoden, die das Unterhalten von Name/Wert-Paaren vereinfachen. Sie können die Informationen entweder als Attribute oder als Satz untergeordneter Elemente unterhalten.  
  
 Ein Unterschied zwischen diesen beiden Formen besteht darin, dass Attribute der Beschränkung unterliegen, dass pro Element immer nur ein Attribut mit einem bestimmten Namen vorhanden sein darf. Für untergeordnete Elemente gilt diese Einschränkung nicht.  
  
## <a name="setattributevalue-and-setelementvalue"></a>"SetAttributeValue" und "SetElementValue"  
 Zum Unterhalten von Name/Wert-Paaren stehen die folgenden beiden Methoden zur Verfügung: <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> und <xref:System.Xml.Linq.XElement.SetElementValue%2A>. Diese beiden Methoden besitzen eine ähnliche Semantik.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> können Attribute eines Elements hinzufügen, ändern oder entfernen.  
  
- Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines Attributs aufrufen, das nicht existiert, erstellt die Methode ein neues Attribut und fügt dieses dem angegebenen Element hinzu.  
  
- Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines vorhandenen Attributs und einem angegebenen Inhalt aufrufen, wird der Inhalt des Attributs durch den angegebenen Inhalt ersetzt.  
  
- Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines vorhandenen Attributs aufrufen und für den Inhalt einen NULL-Wert angeben, wird das Attribut aus dem übergeordneten Element entfernt.  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A> können untergeordnete Elemente eines Elements hinzufügen, ändern oder entfernen.  
  
- Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines untergeordneten Elements aufrufen, das nicht existiert, erstellt die Methode ein neues Element und fügt dieses dem angegebenen Element hinzu.  
  
- Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines vorhandenen Elements und einem angegebenen Inhalt aufrufen, wird der Inhalt des Elements durch den angegebenen Inhalt ersetzt.  
  
- Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines vorhandenen Elements aufrufen und für den Inhalt einen NULL-Wert angeben, wird das Element aus dem übergeordneten Element entfernt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Element, das keine Attribute besitzt. Es verwendet dann die <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>-Methode, um eine Liste von Name/Wert-Paaren zu erstellen und zu unterhalten.  
  
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
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Element, das keine untergeordneten Elemente besitzt. Es verwendet dann die <xref:System.Xml.Linq.XElement.SetElementValue%2A>-Methode, um eine Liste von Name/Wert-Paaren zu erstellen und zu unterhalten.  
  
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
  
```xml  
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

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
