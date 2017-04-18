---
title: "Spät gebundene Auflösung. Laufzeitfehler sind möglich | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
dev_langs:
- VB
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ac885b0de2c4f44d4323487fc55cde9b23defa4
ms.lasthandoff: 03/13/2017

---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Spät gebundene Auflösung. Laufzeitfehler sind möglich.
Ein Objekt einer deklarierten Variablen zugewiesen ist die [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Wenn Sie eine Variable deklarieren `Object`, muss der Compiler eine *späte Bindung*, wodurch zusätzliche Operationen zur Laufzeit. Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus. Angenommen, Sie weisen eine <xref:System.Windows.Forms.Form>auf die `Object` Variable, und wiederholen Sie den Zugriff auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>-Eigenschaft, löst die Laufzeit eine <xref:System.MemberAccessException>da die <xref:System.Windows.Forms.Form>Klasse macht eine `NameTable` Eigenschaft.</xref:System.Windows.Forms.Form> </xref:System.MemberAccessException> </xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> </xref:System.Windows.Forms.Form>  
  
 Wenn Sie die Variable eines bestimmten Typs deklarieren, kann der Compiler ausführen *frühe Bindung* zum Zeitpunkt der Kompilierung. Dies führt zu einer Leistungssteigerung, kontrollierten Zugriff auf die Member des angegebenen Typs und einer besseren Lesbarkeit des Codes.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42017  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn möglich, deklarieren Sie die Variable eines bestimmten Typs sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
