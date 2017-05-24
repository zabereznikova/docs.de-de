---
title: Beibehalten von Leerzeichen beim Serialisieren3 | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1d6cebecd75bedc393b06261c1955a554c9cf18c
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="preserving-white-space-while-serializing"></a>Beibehalten von Leerzeichen beim Serialisieren
In diesem Thema wird beschrieben, wie Sie das Leerraumverhalten beim Serialisieren von XML-Strukturen steuern können.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Leerraumverhalten von Methoden, die XML-Strukturen serialisieren  
 Die folgenden Methoden in den Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument> serialisieren eine XML-Struktur. Sie können XML-Strukturen in eine Datei, in einen <xref:System.IO.TextReader> oder in einen <xref:System.Xml.XmlReader> serialisieren. Die `ToString`-Methode nimmt eine Serialisierung in eine Zeichenfolge vor.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName>  
  
 Wenn die Methode nicht <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, formatiert die Methode den serialisierten XML-Code, indem sie ihn mit Einzügen versieht. In diesem Fall wird der gesamte nicht signifikante Leerraum in der XML-Struktur verworfen.  
  
 Wenn die Methode <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, können Sie angeben, dass der serialisierte XML-Code nicht formatiert (eingerückt) werden soll. In diesem Fall wird der gesamte Leerraum in der XML-Struktur beibehalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisieren von XML-Strukturen (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
