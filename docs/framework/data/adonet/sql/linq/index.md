---
title: LINQ to SQL
description: LINQ to SQL ist eine Komponente des .NET Framework, die eine Lauf Zeit Infrastruktur zum Verwalten relationaler Daten als Objekte bereitstellt.
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: d6fadecf17cae21527cec2180b6d6c5b5e85d0cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551313"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist eine Komponente von .NET Framework Version 3,5, die eine Lauf Zeit Infrastruktur zum Verwalten relationaler Daten als Objekte bereitstellt.  
  
> [!NOTE]
> Relationale Daten erscheinen als Auflistung zweidimensionaler Tabellen (*Beziehungen* oder *Flatfiles*), bei denen gemeinsame Spalten Tabellen verbinden. Zur effektiven Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie mit den zugrunde liegenden Prinzipien relationaler Datenbanken vertraut sein.  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist. Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] diese zurück in Objekte, die Sie mit Ihrer eigenen Programmiersprache bearbeiten können.  
  
 Entwickler, die Visual Studio verwenden, verwenden in der Regel das objektrelationaler Designer, das eine Benutzeroberfläche für die Implementierung zahlreicher Funktionen von bietet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
 Die Dokumentation zu diesem Release von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] beschreibt die grundlegenden Bausteine, Verfahren und Techniken zur Erstellung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen. Sie können auch Microsoft-Dokumentation auf bestimmte Probleme durchsuchen, und Sie können am [LINQ-Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)teilnehmen, in dem Sie komplexere Themen ausführlich mit Experten erörtern können. Zum Schluss ist die [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) Whitepaper Details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Technology, Complete with Visual Basic und c# Code examples (in englischer Sprache).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erste Schritte](getting-started.md)  
 Bietet eine komprimierte Übersicht über [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sowie Informationen zu den ersten Schritten mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Programmierhandbuch](programming-guide.md)  
 Bietet schrittweise Anleitungen für Zuordnung, Abfrage, Update, Debugging und ähnlichen Aufgaben.  
  
 [Verweis](reference.md)  
 Enthält Referenzinformationen zu verschiedenen Aspekten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Programmierung. Die Themen umfassen SQL-CLR-Typzuordnung, Übersetzung von Standardabfrageoperatoren und mehr.  
  
 [Beispiele](samples.md)  
 Enthält Links zu Visual Basic-und c#-Beispielen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Language-Integrated Query (LINQ)-C #](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Bietet Übersichten von LINQ-Technologien in c#.

 [Language Integrated Query (LINQ) – Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Stellt Übersichten von LINQ-Technologien in Visual Basic bereit.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Beschreibt LINQ-Technologien für Visual Basic Benutzer.  
  
 [LINQ und ADO.NET](../../linq-and-ado-net.md)  
 Links zum ADO.net-Portal.  
  
 [LINQ to SQL Walkthroughs (Exemplarische Vorgehensweisen für LINQ to SQL)](/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Listet exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.  
  
 [Herunterladen von Beispieldatenbanken](downloading-sample-databases.md)  
 Beschreibt, wie die in der Dokumentation verwendeten Beispieldatenbanken heruntergeladen werden.  
  
 [Übersicht über das LinqDataSource-Webserver Steuerelement](/previous-versions/aspnet/bb547113(v=vs.100))  
 Beschreibt, wie das- <xref:System.Web.UI.WebControls.LinqDataSource> Steuerelement LINQ (Language-Integrated Query) für Webentwickler über die Architektur des ASP.NET-Datenquellen-Steuer Elements verfügbar macht.
