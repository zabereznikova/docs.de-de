---
title: "Gewusst wie: Erstellen einer privaten Schriftartenauflistung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Schriftarten, Erstellen von privaten Auflistungen"
  - "Private Schriftartauflistungen, Erstellen"
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Erstellen einer privaten Schriftartenauflistung
Die <xref:System.Drawing.Text.PrivateFontCollection>\-Klasse erbt von der abstrakten <xref:System.Drawing.Text.FontCollection>\-Basisklasse.  Mithilfe eines <xref:System.Drawing.Text.PrivateFontCollection>\-Objekts können Sie eine Gruppe von Schriftarten verwalten, die speziell für eine Anwendung verwendet werden.  Eine private Schriftartensammlung kann sowohl installierte Systemschriftarten als auch Schriftarten umfassen, die nicht auf dem Computer installiert sind.  Um einer privaten Schriftartenauflistung eine Schriftartdatei hinzuzufügen, rufen Sie die <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A>\-Methode eines <xref:System.Drawing.Text.PrivateFontCollection>\-Objekts auf.  
  
 Die <xref:System.Drawing.Text.FontCollection.Families%2A>\-Eigenschaft eines <xref:System.Drawing.Text.PrivateFontCollection>\-Objekts enthält ein Array von <xref:System.Drawing.FontFamily>\-Objekten.  
  
 Die Anzahl der Schriftfamilien in einer privaten Schriftartensammlung muss nicht unbedingt mit der Anzahl der Schriftartdateien übereinstimmen, die der Sammlung hinzugefügt wurden.  Angenommen, Sie fügen der Sammlung die Dateien **ArialBd.tff**, **Times.tff** und **TimesBd.tff** hinzu.  Die Sammlung enthält daraufhin drei Dateien, aber nur zwei Kategorien, da **Times.tff** und **TimesBd.tff** derselben Kategorie angehören.  
  
## Beispiel  
 Im folgenden Beispiel werden einem <xref:System.Drawing.Text.PrivateFontCollection>\-Objekt die folgenden drei Schriftartdateien hinzugefügt:  
  
-   C:\\*Systemstamm*\\Fonts\\Arial.tff \(Arial, Standard\)  
  
-   C:\\*Systemstamm*\\Fonts\\CourBI.tff \(Courier New, Fett kursiv\)  
  
-   C:\\*Systemstamm*\\Fonts\\TimesBd.tff \(Times New Roman, Fett\)  
  
 Durch den Code wird ein Array von <xref:System.Drawing.FontFamily>\-Objekten aus der <xref:System.Drawing.Text.FontCollection.Families%2A>\-Eigenschaft des <xref:System.Drawing.Text.PrivateFontCollection>\-Objekts abgerufen.  
  
 Für jedes <xref:System.Drawing.FontFamily>\-Objekt in der Auflistung ruft der Code die <xref:System.Drawing.FontFamily.IsStyleAvailable%2A>\-Methode auf, um festzustellen, ob verschiedene Schriftschnitte \(Normal, Fett, Kursiv, Fett Kursiv, Unterstrichen und Durchgestrichen\) verfügbar sind.  Die an die <xref:System.Drawing.FontFamily.IsStyleAvailable%2A>\-Methode übergebenen Argumente sind Member der <xref:System.Drawing.FontStyle>\-Enumeration.  
  
 Wenn eine bestimmte Kategorie\-\/Schriftschnittkombination verfügbar ist, wird anhand dieser Kategorie und dieses Schriftschnitts ein <xref:System.Drawing.Font>\-Objekt erstellt.  Das erste an den <xref:System.Drawing.Font.%23ctor%2A>\-Konstruktor übergebene Argument entspricht dem Namen der Schriftfamilie \(keinem <xref:System.Drawing.FontFamily>\-Objekt, wie dies bei anderen Varianten des <xref:System.Drawing.Font.%23ctor%2A>\-Konstruktors der Fall ist\).  Nach seiner Erstellung wird das <xref:System.Drawing.Font>\-Objekt an die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse übergeben, damit der Kategoriename zusammen mit dem Namen des Schriftschnitts angezeigt wird.  
  
 Das Ergebnis des nachstehenden Codes ist vergleichbar mit dem Ergebnis in der folgenden Abbildung.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Die Datei Arial.tff \(die der privaten Schriftartenauflistung im folgenden Codebeispiel hinzugefügt wurde\) ist die Schriftartdatei für die Schriftart Arial mit dem Schriftschnitt Normal.  Beachten Sie jedoch, dass das Programm für die Schriftfamilie Arial außer "Normal" mehrere andere verfügbare Schriftschnitte ausgibt.  Dies liegt daran, dass [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] in der Lage ist, ausgehend vom Schriftschnitt Normal die Schriftschnitte Fett, Kursiv sowie Fett Kursiv zu simulieren.  Außerdem kann [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] die Effekte Unterstrichen und Durchgestrichen vom Schriftschnitt Normal ableiten.  
  
 Entsprechend kann [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ausgehend vom Schriftschnitt Fett oder Kursiv den Schriftschnitt Fett Kursiv simulieren.  Das Programm gibt für die Kategorie Times "Fett Kursiv" als verfügbaren Schriftschnitt aus, obwohl **TimesBd.tff** \(Times New Roman Fett\) die einzige Times\-Datei in der Sammlung ist.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 <xref:System.Drawing.Text.PrivateFontCollection>   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)