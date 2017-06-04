---
title: "Creating the GamePiece Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37a27a86-ac1c-47be-b477-cb4b819459d3
caps.latest.revision: 9
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 9
---
# Creating the GamePiece Class
Die**GamePiece**\-Klasse kapselt die gesamte Funktionalität, die für folgende Schritte erforderlich ist: Laden eines Microsoft XNA\-Spielsteinbilds, Nachverfolgen des Mauszustands im Verhältnis zum Spielstein, Erfassen der Maus, Bereitstellen der Manipulations\- und Trägheitsverarbeitung und Bereitstellen der Funktion zum Abprallen, wenn der Spielstein die Grenzen des Viewports erreicht.  
  
## Private Member  
 Im oberen Bereich der **GamePiece**\-Klasse werden mehrere private Member deklariert.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privatemembers)]  
  
## Öffentliche Eigenschaften  
 Drei dieser privaten Member werden über öffentliche Eigenschaften verfügbar gemacht.  Die Eigenschaften **Scale** und **PieceColor** ermöglichen der Anwendung das Angeben der Skalierung und der Farbe des Spielsteins.  Die **Bounds**\-Eigenschaft wird verfügbar gemacht, damit ein Spielstein die Grenzen eines anderen Spielsteins zum Rendern verwenden kann, z. B. wenn ein Spielstein einen anderen überlagern soll.  Der folgende Code veranschaulicht die Deklaration der öffentlichen Eigenschaften.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PublicProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_publicproperties)]  
  
## Klassenkonstruktor  
 Der Konstruktor für die **GamePiece**\-Klasse akzeptiert die folgenden Parameter:  
  
-   A. Einen [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx)\-Typ.  Der hier übergebene Verweis wird dem privaten `spriteBatch`\-Member zugewiesen und zum Zugreifen auf die [SpriteBatch.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.draw.aspx)\-Methode verwendet, wenn sich der Spielstein rendert.  Außerdem werden mithilfe der [GraphicsDevice](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.graphicsdevice.aspx)\-Eigenschaft das [Texture](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.texture.aspx)\-Objekt erstellt, das dem Spielstein zugeordnet ist, und die Größe des Viewports abgerufen. Auf diese Weise kann ermittelt werden, wann der Spielstein auf eine Fensterbegrenzung trifft und abprallt.  
  
-   Eine Zeichenfolge, die den Dateinamen des Bilds angibt, das für den Spielstein verwendet werden soll.  
  
 Der Konstruktor erstellt auch ein <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D>\-Objekt und ein <xref:System.Windows.Input.Manipulations.InertiaProcessor2D>\-Objekt und richtet für deren Ereignisse Ereignishandler ein.  
  
 Der folgende Code veranschaulicht den Konstruktor für die **GamePiece**\-Klasse.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Constructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_constructor)]  
  
## Erfassen der Mauseingabe  
 Die **UpdateFromMouse**\-Methode erkennt, wenn eine Maustaste gedrückt wird, während sich die Maus innerhalb der Grenzen des Spielsteins befindet, und wenn die Maustaste losgelassen wird.  
  
 Wenn die linke Maustaste gedrückt gehalten wird \(während sich die Maus innerhalb der Grenzen des Spielsteins befindet\), gibt diese Methode mithilfe eines Flags an, dass dieser Spielstein die Maus erfasst hat, und startet die Manipulationsverarbeitung.  
  
 Die Manipulationsverarbeitung wird gestartet, indem ein Array mit <xref:System.Windows.Input.Manipulations.Manipulator2D>\-Objekten erstellt und an das <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D>\-Objekt übergeben wird.  Dies bewirkt, dass der Manipulationsprozessor die Manipulatoren \(in diesem Fall ein einzelner Manipulator\) auswertet und Manipulationsereignisse auslöst.  
  
 Außerdem wird der Punkt gespeichert, an dem das Ziehen auftritt.  Dies wird später während des <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta>\-Ereignisses verwendet, um die Deltaübersetzungswerte anzupassen, damit der Spielstein hinter dem Ziehpunkt ausgerichtet wird.  
  
 Als Letztes gibt diese Methode den Zustand der Mausauswahl zurück.  Das [GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)\-Objekt kann den Auswahlvorgang auch dann verwalten, wenn mehrere Spielsteine vorhanden sind.  
  
 Der folgende Code veranschaulicht die **UpdateFromMouse**\-Methode.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_updatefrommouse)]  
  
## Verarbeiten von Manipulationen  
 Zu Beginn der Manipulation wird das <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Started>\-Ereignis ausgelöst.  Der Handler für dieses Ereignis hält die Trägheitsverarbeitung an, falls diese aktiv ist, und legt das *processInertia*\-Flag auf `false` fest.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationStarted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationstarted)]  
  
 Wenn sich die Werte ändern, die der Manipulationsänderung zugeordnet sind, wird das <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta>\-Ereignis ausgelöst.  Der Handler für dieses Ereignis verwendet die Deltawerte, die in den Ereignisargumenten übergeben werden, um Änderungen an den Positions\- und Drehungswerten des Spielsteins vorzunehmen.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationdelta)]  
  
 Wenn alle Manipulatoren \(in diesem Fall nur ein Manipulator\) entfernt werden, die einer Manipulation zugeordnet sind, löst der Manipulationsprozessor das <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed>\-Ereignis aus.  Der Handler für dieses Ereignis startet die Trägheitsverarbeitung, indem er die ursprünglichen Geschwindigkeiten des Trägheitsprozessors auf die Geschwindigkeiten festlegt, die von den Ereignisargumenten gemeldet werden. Außerdem legt er das *processInertia*\-Flag auf `true` fest.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationcompleted)]  
  
## Verarbeiten der Trägheit  
 Während die Trägheitsverarbeitung neue Werte für Winkelfrequenzen und lineare Geschwindigkeiten, Positionskoordinaten \(Übersetzung\) und Drehungen extrapoliert, wird das <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>\-Ereignis ausgelöst.  Der Handler für dieses Ereignis verwendet die Deltawerte, die in den Ereignisargumenten übergeben werden, um Änderungen an der Position und Drehung des Spielsteins vorzunehmen.  
  
 Falls die neuen Koordinaten dazu führen, dass der Spielstein über die Grenzen des Viewports hinaus verschoben wird, wird die Geschwindigkeit der Trägheitsverarbeitung umgekehrt.  Dies bewirkt, dass der Spielstein von der Viewportgrenze zurückspringt, auf die er gestoßen ist.  
  
 Sie können die Eigenschaften eines <xref:System.Windows.Input.Manipulations.InertiaProcessor2D>\-Objekts nicht ändern, während es die Extrapolierung durchführt.  Aus diesem Grund stoppt der Ereignishandler beim Umkehren der X\- oder Y\-Geschwindigkeit zuerst die Trägheit, indem er die <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Complete%2A>\-Methode aufruft.  Anschließend weist er die neuen Anfangsgeschwindigkeitswerte als aktuelle Geschwindigkeitswerte zu \(angepasst für "Schwammverhalten"\) und legt das *processInertia*\-Flag auf `true` fest.  
  
 Der folgende Code veranschaulicht den Ereignishandler für das <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>\-Ereignis.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiadelta)]  
  
 Nachdem die Trägheitsverarbeitung abgeschlossen ist, löst der Trägheitsprozessor das <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Completed>\-Ereignis aus.  Der Handler für dieses Ereignis legt das *processInertia*\-Flag auf `false` fest.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiacompleted)]  
  
 Keine der bisher beschriebenen Logiken bewirkt das Auftreten der Trägheitsextrapolierung.  Dies wird mithilfe der **ProcessInertia**\-Methode erreicht.  Diese Methode, die von der Aktualisierungsschleife des Spiels \([Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)\-Methode\) wiederholt aufgerufen wird, überprüft, ob das *processInertia*\-Flag auf `true` festgelegt ist. Wenn das zutrifft, wird die <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Process%2A>\-Methode aufgerufen.  Das Aufrufen dieser Methode bewirkt, dass die Extrapolierung durchgeführt und das <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>\-Ereignis ausgelöst wird.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_ProcessInertia](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_processinertia)]  
  
 Der Spielstein wird erst gerendert, wenn eine der Überladungen der Draw\-Methode aufgerufen wird.  Die erste Überladung dieser Methode wird wiederholt von der Ziehschleife des Spiels \([Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)\-Methode\) aufgerufen.  Der Spielstein wird dann mit den aktuellen Positions\-, Drehungs\- und Skalierungsfaktoren gerendert.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Draw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_draw)]  
  
## Zusätzliche Eigenschaften  
 Drei private Eigenschaften werden von der **GamePiece**\-Klasse verwendet.  
  
1.  **Timestamp** – Ruft einen Timestampwert ab, der von den Manipulations\- und Trägheitsprozessoren verwendet werden soll.  
  
2.  **X** – Ruft die X\-Koordinate des Spielsteins ab bzw. legt diese fest.  Beim Festlegen werden die Grenzen für Treffertests und die Pivotposition des Manipulationsprozessors angepasst.  
  
3.  **Y** – Ruft die Y\-Koordinate des Spielsteins ab bzw. legt diese fest.  Beim Festlegen werden die Grenzen für Treffertests und die Pivotposition des Manipulationsprozessors angepasst.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privateproperties)]  
  
## Siehe auch  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)   
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)