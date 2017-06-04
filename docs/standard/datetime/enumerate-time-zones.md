---
title: "Gewusst wie: Auflisten der auf einem Computer vorhandenen Zeitzonen | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Auflisten von Zeitzonen [.NET Framework]"
  - "Zeitzonen [.NET Framework], Auflisten"
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Auflisten der auf einem Computer vorhandenen Zeitzonen
Damit eine festgelegte Zeitzone erfolgreich verwendet werden kann, müssen die Zeitzonendaten auf dem System vorhanden sein.  Bei den Betriebssystemen Windows XP und Windows Vista werden diese Informationen in der Registrierung gespeichert.  Die Registrierung enthält nur Daten zu einigen Zeitzonen, obwohl die Gesamtzahl der Zeitzonen auf der Welt sehr groß ist.  Darüber hinaus ist die Registrierung auch eine dynamische Struktur, deren Inhalt versehentlich oder absichtlich geändert werden kann.  Daher kann eine Anwendung nicht immer davon ausgehen, dass eine bestimmte Zeitzone definiert und im System verfügbar ist.  Viele Anwendungen, die Zeitzonendaten verwenden, ermitteln zunächst, ob die benötigten Zeitzonen auf dem lokalen System verfügbar sind, oder sie stellen dem Benutzer eine Liste mit Zeitzonen zur Verfügung, aus denen er auswählen muss.  Hierfür muss eine Anwendung die auf einem lokalen System definierten Zeitzonen auflisten.  
  
> [!NOTE]
>  Wenn für eine Anwendung eine bestimmte Zeitzone vorhanden sein muss, die möglicherweise nicht auf dem lokalen System definiert ist, kann die Anwendung das Vorhandensein dieser Zeitzone sicherstellen, indem sie die Zeitzonendaten serialisiert und anschließend deserialisiert.  Die Zeitzone kann dann einem Listensteuerelement hinzugefügt werden, damit der Benutzer sie auswählen kann.  Ausführliche Informationen finden Sie unter [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und unter [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
### So listen Sie die auf dem lokalen System vorhandene Zeitzonen auf  
  
1.  Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName>\-Methode auf.  Die Methode gibt eine allgemeine <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>\-Auflistung von <xref:System.TimeZoneInfo>\-Objekten zurück.  Die Einträge in die Auflistung werden nach ihrer <xref:System.TimeZoneInfo.DisplayName%2A>\-Eigenschaft sortiert.  Beispiel:  
  
     [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
     [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]  
  
2.  Führen Sie die einzelnen <xref:System.TimeZoneInfo>\-Objekte in der Auflistung auf, indem Sie eine `foreach`\-Schleife \(in C\#\) oder eine `For Each`…`Next`\-Schleife \(in Visual Basic\) verwenden, und verarbeiten Sie die einzelnen Objekte wie erforderlich.  Mit dem folgenden Code werden beispielsweise die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>\-Auflistung der <xref:System.TimeZoneInfo>\-Objekte, die in Schritt 1 zurückgegeben wurden, und der Anzeigename der einzelnen Zeitzonen auf der Konsole aufgeführt.  
  
     [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
     [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]  
  
### So zeigen Sie eine Liste der auf dem lokalen System vorhandenen Zeitzonen für den Benutzer an  
  
1.  Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName>\-Methode auf.  Die Methode gibt eine allgemeine <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>\-Auflistung von <xref:System.TimeZoneInfo>\-Objekten zurück.  
  
2.  Weisen Sie die in Schritt 1 zurückgegebene Auflistung der `DataSource`\-Eigenschaft eines Windows Forms\- oder ASP.NET\-Listensteuerelements zu.  
  
3.  Rufen Sie das <xref:System.TimeZoneInfo>\-Objekt ab, das der Benutzer ausgewählt hat.  
  
 Das Beispiel veranschaulicht dies anhand einer Windows\-Anwendung.  
  
## Beispiel  
 Im Beispiel wird eine Windows\-Anwendung gestartet, die die im System definierten Zeitzonen in einem Listenfeld anzeigt.  Im Beispiel wird anschließend ein Dialogfeld angezeigt, das den Wert der <xref:System.TimeZoneInfo.DisplayName%2A>\-Eigenschaft des Zeitzonenobjekts enthält, das der Benutzer ausgewählt hat.  
  
 [!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
 [!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]  
  
 Die meisten Listensteuerelemente \(z. B. das <xref:System.Windows.Forms.ListBox?displayProperty=fullName>\- Steuerelement oder das <xref:System.Web.UI.WebControls.BulletedList?displayProperty=fullName>\-Steuerelement\) ermöglichen Ihnen, der `DataSource`\-Eigenschaft eine Auflistung von Objektvariablen zuzuweisen, solange diese Auflistung die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert. \(Dies ist beispielsweise bei der allgemeinen <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>\-Klasse der Fall.\) Um ein einzelnes Objekt der Auflistung anzuzeigen, ruft das Steuerelement die `ToString`\-Methode des Objekts auf, um die Zeichenfolge, die das Objekt repräsentiert, zu extrahieren.  Bei <xref:System.TimeZoneInfo>\-Objekten gibt die `ToString`\-Methode den Anzeigenamen des <xref:System.TimeZoneInfo>\-Objekts zurück \(der Wert seiner <xref:System.TimeZoneInfo.DisplayName%2A>\-Eigenschaft\).  
  
> [!NOTE]
>  Da Listensteuerelemente die `ToString`\-Methode eines Objekts aufrufen, können Sie dem Steuerelement eine Auflistung von <xref:System.TimeZoneInfo>\-Objekten zuweisen, im Steuerelement einen aussagekräftigen Namen für die einzelnen Objekte anzeigen und das <xref:System.TimeZoneInfo>\-Objekt abrufen, das der Benutzer ausgewählt hat.  Hierdurch entfällt die Notwendigkeit, eine Zeichenfolge für jedes Objekt in der Auflistung zu extrahieren, die Zeichenfolge einer Auflistung zuzuweisen, die wiederum der `DataSource`\-Eigenschaft des Steuerelements zugewiesen wird, die vom Benutzer ausgewählte Zeichenfolge abzurufen und diese Zeichenfolge anschließend zum Extrahieren des beschriebenen Objekts zu verwenden.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Die folgenden Namespaces müssen importiert werden:  
  
     <xref:System> \(in C\#\-Code\)  
  
     <xref:System.Collections.ObjectModel>  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)   
 [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)