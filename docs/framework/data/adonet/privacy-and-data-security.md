---
title: "Datenschutz und Datensicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 46fa5839-adf7-4c7c-bce3-71e941fa7de9
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Datenschutz und Datensicherheit
Die Vorgehensweise zum Schutz und zur Verwaltung sicherheitsrelevanter Informationen in ADO.NET\-Anwendungen hängt von den Produkten und Technologien ab, mit denen die jeweilige Anwendung erstellt wird.  ADO.NET selbst stellt keine direkten Dienste zum Sichern oder Verschlüsseln von Daten bereit.  
  
## Kryptografie und Hashcodes  
 Die Klassen im .NET Framework\-<xref:System.Security.Cryptography>\-Namespace können in Ihren ADO.NET\-Anwendungen verwendet werden, um zu verhindern, dass Daten von Unbefugten gelesen oder verändert werden können.  Einige Klassen sind Wrapper für die nicht verwaltete Microsoft CryptoAPI, während es sich bei anderen um verwaltete Implementierungen handelt.  Das Thema [Cryptographic Services](http://msdn.microsoft.com/de-de/68a1e844-c63c-44af-9247-f6716eb23781) bietet eine Übersicht über die Kryptografieoptionen in .NET Framework und beschreibt die Implementierung der Kryptografiefunktionen sowie die Ausführung bestimmter Kryptografieaufgaben.  
  
 Anders als bei der Kryptografie, die das Verschlüsseln und anschließende Entschlüsseln von Daten ermöglicht, ist das Erstellen von Hashwerten von Daten \(Hashing\) ein unidirektionaler Vorgang.  Das Hashing von Daten empfiehlt sich, wenn Sie unbefugte Manipulationen Ihrer Daten verhindern möchten, indem Sie überprüfen, dass die Daten nicht geändert wurden: Bei identischen Eingabezeichenfolgen produzieren Hashalgorithmen immer identische kurze Ausgabewerte, die leicht miteinander verglichen werden können.  [Ensuring Data Integrity with Hash Codes](../../../../docs/standard/security/ensuring-data-integrity-with-hash-codes.md) beschreibt, wie Sie Hashwerte generieren und überprüfen können.  
  
## Verschlüsseln von Konfigurationsdateien  
 Eines der wichtigsten Ziele beim Sichern einer Anwendung besteht darin, den Zugriff auf die Datenquelle zu schützen.  Eine Verbindungszeichenfolge stellt ein potenzielles Sicherheitsrisiko dar, wenn sie nicht gesichert wird.  In Konfigurationsdateien gespeicherte Verbindungszeichenfolgen werden in Standard\-XML\-Dateien gespeichert, für die .NET Framework einen gemeinsamen Satz von Elementen definiert hat.  Die geschützte Konfiguration ermöglicht es Ihnen, sicherheitsrelevante Informationen in einer Konfigurationsdatei zu verschlüsseln.  Sie wurde zwar primär für ASP.NET\-Anwendungen entwickelt, kann aber auch zum Verschlüsseln von Konfigurationsdateiabschnitten in Windows\-Anwendungen verwendet werden.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Sichern von Zeichenfolgenwerten im Arbeitsspeicher  
 Wenn ein <xref:System.String>\-Objekt sicherheitsrelevante Informationen enthält \(z. B. Kennwörter, Kreditkartennummern oder persönliche Daten\), besteht das Risiko, dass diese Informationen nach ihrer Verwendung in die falschen Hände gelangen, weil die Anwendung die Daten nicht aus dem Arbeitsspeicher des Computers löschen kann.  
  
 Eine <xref:System.String> ist unveränderbar. Einmal erstellt, kann ihr Wert kann nicht mehr geändert werden.  Änderungen, die den Zeichenfolgenwert scheinbar verändern, erstellen in Wirklichkeit eine neue Instanz eines <xref:System.String>\-Objekts im Arbeitsspeicher, wobei die Daten als Klartext gespeichert werden.  Außerdem ist es nicht möglich vorherzusagen, wann die Zeichenfolgeninstanzen aus dem Arbeitsspeicher gelöscht werden.  Die Arbeitsspeicherfreigabe mit Zeichenfolgen ist bei der .NET\-Garbage Collection nicht deterministisch.  Wenn Ihre Daten wirklich sicherheitsrelevant sind, sollten Sie die Verwendung der Klassen <xref:System.String> und <xref:System.Text.StringBuilder> vermeiden.  
  
 Die <xref:System.Security.SecureString>\-Klasse stellt Methoden zum Verschlüsseln von Text mit der Datenschutz\-API \(DPAPI\) im Arbeitsspeicher bereit.  Die Zeichenfolge wird dann aus dem Arbeitsspeicher gelöscht, wenn sie nicht mehr benötigt wird.  Es gibt keine `ToString`\-Methode zum schnellen Lesen des Inhalts einer <xref:System.Security.SecureString>.  Sie können eine neue Instanz von `SecureString` ohne Wert oder durch Übergabe eines Zeigers auf ein Array von <xref:System.Char>\-Objekten initialisieren.  Anschließend können Sie dann die verschiedenen Methoden der Klasse verwenden, um mit der Zeichenfolge zu arbeiten.  Weitere Informationen erhalten Sie, wenn Sie das [Anwendungsbeispiel für SecureString](http://go.microsoft.com/fwlink/?LinkId=120418) herunterladen, das veranschaulicht, wie die `SecureString`\-Klasse verwendet wird.  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [SQL Server\-Sicherheit](../../../../docs/framework/data/adonet/sql/sql-server-security.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)