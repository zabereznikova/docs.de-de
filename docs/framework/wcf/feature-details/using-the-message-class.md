---
title: "Verwenden der Message-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Verwenden der Message-Klasse
Die <xref:System.ServiceModel.Channels.Message> Klasse ist für die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Die gesamte Kommunikation zwischen Clients und Diensten führt letztlich <xref:System.ServiceModel.Channels.Message> Instanzen gesendet und empfangen.  
  
 Sie würden normalerweise interagiert nicht mit der <xref:System.ServiceModel.Channels.Message> -Klasse direkt verwenden. Stattdessen werden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmodellkonstrukte wie Datenverträge, Nachrichtenverträge und Vorgangsverträge zum Beschreiben von ein- und ausgehenden Nachrichten verwendet. In einigen erweiterten Szenarien jedoch Sie programmieren können, verwenden die <xref:System.ServiceModel.Channels.Message> -Klasse direkt verwenden. Beispielsweise möchten Sie verwenden die <xref:System.ServiceModel.Channels.Message> Klasse:  
  
-   Wenn Sie eine alternative Methode zum Erstellen des Inhalts ausgehender Nachrichten (z. B. Erstellen einer Nachricht direkt aus einer Datei auf der Festplatte) statt des Serialisierens von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Objekten benötigen.  
  
-   Wenn Sie eine alternative Methode zum Verwenden des Inhalts eingehender Nachrichten (z. B. zum Anwenden einer XSLT-Transformation auf den unformatierten XML-Inhalt) statt des Deserialisierens in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Objekte benötigen.  
  
-   Wenn Sie Nachrichten allgemein und unabhängig vom Nachrichteninhalt bearbeiten müssen (z. B. zum Routen oder Weiterleiten von Nachrichten beim Erstellen eines Routers, Lastenausgleichsmoduls oder Veröffentlichen-Abonnieren-Systems).  
  
 Vor der Verwendung der <xref:System.ServiceModel.Channels.Message> Klasse, die sich mit vertraut machen, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Architektur für die Datenübertragung [Übersicht über die Architektur von Data Transfer](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
 Ein <xref:System.ServiceModel.Channels.Message> ist ein allzweckcontainer für Daten, ihr Design folgt aber eng das Design einer Nachricht in das SOAP-Protokoll. Wie in SOAP verfügt eine Nachricht über einen Nachrichtentext und einen Header. Der Nachrichtentext enthält die tatsächlichen Nutzlastdaten, während die Header zusätzliche benannte Datencontainer enthalten. Die Regeln für das Lesen und Schreiben von Text und Headern sind unterschiedlich, so werden die Header immer im Arbeitsspeicher gepuffert, und der Zugriff ist beliebig oft in beliebiger Reihenfolge möglich, während der Text nur einmal gelesen und in einem Stream übertragen werden kann. Normalerweise werden in SOAP der Nachrichtentext dem SOAP-Text und die Nachrichtenheader den SOAP-Headern zugeordnet.  
  
## <a name="using-the-message-class-in-operations"></a>Verwenden der Meldungsklasse in Vorgängen  
 Sie können die <xref:System.ServiceModel.Channels.Message> Klasse als Eingabeparameter eines Vorgangs, der Rückgabewert eines Vorgangs oder beides. Wenn <xref:System.ServiceModel.Channels.Message> wird an einer beliebigen Stelle in einem Vorgang gelten die folgenden Einschränkungen:  
  
-   Der Vorgang kann über keinen `out`-Parameter oder `ref`-Parameter verfügen.  
  
-   Es kann nicht mehr als einen `input`-Parameter geben. Wenn der Parameter vorhanden ist, muss er entweder eine Nachricht oder ein Nachrichtenvertragstyp sein.  
  
-   Der Rückgabetyp muss entweder `void`, `Message` oder ein Nachrichtenvertragstyp sein.  
  
 Das folgende Codebeispiel enthält einen gültigen Vorgangsvertrag.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>Erstellen grundlegender Nachrichten  
 Die <xref:System.ServiceModel.Channels.Message> -Klasse stellt statische `CreateMessage` Factory-Methoden, mit denen Sie grundlegende Nachrichten erstellen.  
  
 Alle `CreateMessage` Überladungen nehmen einen Versionsparameter vom Typ <xref:System.ServiceModel.Channels.MessageVersion> , der angibt, der SOAP und WS-Addressing-Versionen, für die Nachricht verwendet. Wenn Sie die gleichen Protokollversionen wie die eingehende Nachricht verwenden möchten, können Sie die <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> Eigenschaft auf die <xref:System.ServiceModel.OperationContext> Instanz von abgerufen der <xref:System.ServiceModel.OperationContext.Current%2A> Eigenschaft. Die meisten `CreateMessage`-Überladungen haben außerdem einen Zeichenfolgenparameter, der die für die Nachricht zu verwendende SOAP-Aktion angibt. Die Version kann auf `None` festgelegt werden, um die Generierung des SOAP-Umschlags zu deaktivieren; die Nachricht besteht nur aus dem Text.  
  
## <a name="creating-messages-from-objects"></a>Erstellen von Nachrichten aus Objekten  
 Die grundlegendste `CreateMessage`-Überladung, die nur eine Version und eine Aktion annimmt, erstellt eine Nachricht, die keinen Text enthält. Eine andere Überladung nimmt einen zusätzlichen <xref:System.Object> Parameter; Dadurch wird eine Nachricht erstellt, deren Text die serialisierte Darstellung des angegebenen Objekts. Verwenden der <xref:System.Runtime.Serialization.DataContractSerializer> mit den Standardeinstellungen für die Serialisierung. Wenn Sie ein anderes Serialisierungsprogramm verwenden möchten oder das `DataContractSerializer` anders konfiguriert werden soll, verwenden Sie die `CreateMessage`-Überladung, die auch einen `XmlObjectSerializer`-Parameter annimmt.  
  
 Sie können z. B. zum Zurückgeben eines Objekts in einer Nachricht den folgenden Code verwenden.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>Erstellen von Nachrichten aus XML-Lesern  
 Gibt es `CreateMessage` -Überladungen nehmen ein <xref:System.Xml.XmlReader> oder <xref:System.Xml.XmlDictionaryReader> für den Text anstelle eines Objekts. In diesem Fall enthält der Text der Nachricht die XML, die aus dem Lesen des übergebenen XML-Readers resultiert. Der folgende Code gibt beispielsweise eine Nachricht mit aus einer XML-Datei gelesenem Textinhalt zurück:  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 Darüber hinaus stehen `CreateMessage` -Überladungen nehmen eine <xref:System.Xml.XmlReader> oder <xref:System.Xml.XmlDictionaryReader> , die gesamte Nachricht und nicht nur den Text darstellt. Diese Überladungen nehmen auch einen ganzzahligen `maxSizeOfHeaders`-Parameter an. Header werden immer in den Arbeitsspeicher gepuffert, sobald die Nachricht erstellt wurde, und dieser Parameter begrenzt die stattfindende Pufferung. Dieser Parameter sollte auf einen sicheren Wert festgelegt werden, wenn die XML von einer nicht vertrauenswürdigen Quelle stammt, um einen möglichen Denial-of-Service-Angriff zu vermeiden. Die SOAP-Version und die Version der WS-Adressierung der Nachricht, die der XML-Leser darstellt, müssen mit den durch den Versionsparameter angegebenen Versionen übereinstimmen.  
  
## <a name="creating-messages-with-bodywriter"></a>Erstellen von Nachrichten mit dem Body Writer-Objekt  
 Eine `CreateMessage`-Überladung nimmt eine `BodyWriter`-Instanz an, um den Text der Nachricht zu beschreiben. Ein `BodyWriter` ist eine abstrakte Klasse, die abgeleitet werden kann, um das Erstellen von Nachrichtentexten anzupassen. Sie können eine eigene abgeleitete `BodyWriter`-Klasse erstellen, um Nachrichtentexte benutzerdefiniert zu beschreiben. Müssen Sie überschreiben die `BodyWriter.OnWriteBodyContents` Methode, die eine <xref:System.Xml.XmlDictionaryWriter>; diese Methode ist verantwortlich für das Schreiben des Textes.  
  
 Body Writer-Objekte können gepuffert oder nicht gepuffert (gestreamt) sein. Gepufferte Body Writer-Objekte schreiben ihren Inhalt beliebig oft, während gestreamte Objekte den Inhalt nur einmal schreiben können. Die `IsBuffered`-Eigenschaft gibt an, ob ein Body Writer-Objekt gepuffert ist oder nicht. Sie können dies für das Body Writer-Objekt festlegen, indem Sie den geschützten `BodyWriter`-Konstruktor aufrufen, der einen booleschen `isBuffered`-Parameter annimmt. Body Writer-Objekte unterstützen das Erstellen eines gepufferten Body Writer-Objekts aus einem nicht gepufferten Body Writer-Objekt. Sie können die `OnCreateBufferedCopy`-Methode überschreiben, um diesen Prozess anzupassen. Standardmäßig wird ein Speicherpuffer verwendet, der das von `OnWriteBodyContents` zurückgegebene XML enthält. `OnCreateBufferedCopy` akzeptiert einen ganzzahligen `maxBufferSize`-Parameter. Wenn Sie diese Methode überschreiben, dürfen Sie keine Puffer erstellen, die diese maximale Größe überschreiten.  
  
 Die `BodyWriter`-Klasse bietet die `WriteBodyContents`-Methode und die `CreateBufferedCopy`-Methode, die im Grunde einfache Wrapper um die `OnWriteBodyContents`-Methode bzw. die `OnCreateBufferedCopy`-Methode sind. Diese Methoden führen eine Zustandsprüfung durch, um sicherzustellen, dass auf ein nicht gepuffertes Body Writer-Objekt höchstens einmal zugegriffen wird. Diese Methoden werden nur direkt aufgerufen, wenn benutzerdefinierte abgeleitete `Message`-Klassen erstellt werden, die auf `BodyWriters` basieren.  
  
## <a name="creating-fault-messages"></a>Erstellen von Fehlermeldungen  
 Sie können bestimmte `CreateMessage`-Überladungen verwenden, um SOAP-Fehlermeldungen zu erstellen. Die grundlegendste dieser Überladungen nimmt ein <xref:System.ServiceModel.Channels.MessageFault> -Objekt, das den Fehler beschreibt. Andere Überladungen werden aus Gründen der Benutzerfreundlichkeit bereitgestellt. Die erste solcher Überladungen nimmt einen `FaultCode` und eine Zeichenfolge der Ursache an und erstellt einen `MessageFault` mit `MessageFault.CreateFault` unter Verwendung dieser Informationen. Die andere Überladung nimmt eine Detailobjekt an und übergibt es auch zusammen mit dem Fehlercode und der Ursache an `CreateFault`. So gibt beispielsweise der folgende Vorgang einen Fehler zurück:  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>Extrahieren von Nachrichtentextdaten  
 Die `Message`-Klasse unterstützt mehrere Methoden zum Extrahieren von Informationen aus dem Text. Diese können in die folgenden Kategorien klassifiziert werden:  
  
-   Einmaliges Abrufen des gesamten Nachrichtentexts in einen XML-Writer. Dies wird als bezeichnet *Schreiben einer Nachricht*.  
  
-   Laufenlassen eines XML-Readers über den Nachrichtentext. Dies ermöglicht es Ihnen, später nach Bedarf Stück für Stück auf den Nachrichtentext zuzugreifen. Dies wird als bezeichnet *Lesen einer Nachricht*.  
  
-   Die gesamte Nachricht, einschließlich des Texts in einem Speicherpuffer von kopiert werden die <xref:System.ServiceModel.Channels.MessageBuffer> Typ. Dies wird als bezeichnet *Kopieren einer Nachricht*.  
  
 Sie können unabhängig von der Zugriffsmethode nur einmal auf den Text einer `Message` zugreifen. Ein Nachrichtenobjekt verfügt über eine `State`-Eigenschaft, die anfänglich auf "Erstellt" festgelegt ist. Mit den drei zuvor beschriebenen Zugriffsmethoden wird der Zustand auf "Geschrieben", "Gelesen" bzw. "Kopiert" festgelegt. Darüber hinaus kann eine `Close`-Methode den Zustand auf "Geschlossen" festlegen, wenn der Inhalt des Nachrichtentexts nicht mehr benötigt wird. Auf den Nachrichtentext kann nur im Zustand "Erstellt" zugegriffen werden, und eine Rückkehr zu diesem Zustand ist nach einer Zustandsänderung nicht mehr möglich.  
  
## <a name="writing-messages"></a>Schreiben von Nachrichten  
 Die <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> -Methode schreibt den Inhalt des Texts einer bestimmten `Message` Instanz mit einem angegebenen XML-Writer. Die <xref:System.ServiceModel.Channels.Message.WriteBody%2A> Methode ist identisch, abgesehen davon, dass der Inhalt des Nachrichtentexts in entsprechendes Wrapperelement eingeschlossen (z. B. `soap:body`>). Schließlich <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> schreibt die gesamte Nachricht, einschließlich des umfassenden SOAP-Umschlags und der Header. Bei deaktiviertem SOAP (Version ist `MessageVersion.None`) wird von allen drei Methoden der gleiche Vorgang ausgeführt: Der Inhalt des Nachrichtentexts wird geschrieben.  
  
 Beispielsweise schreibt der folgende Code der Text einer eingehenden Nachricht in eine Datei.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 Zwei zusätzliche Hilfsmethoden schreiben bestimmte SOAP-Startelement-Tags. Diese Methoden haben keinen Zugriff auf den Nachrichtentext, der Nachrichtenzustand wird also nicht geändert. Dazu gehören:  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> schreibt das Start-Textelement, z. B. `<soap:Body>`.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> schreibt das Start-umschlagelement, z. B. `<soap:Envelope>`.  
  
 Rufen Sie zum Schreiben der jeweiligen Endelement-Tags `WriteEndElement` auf dem entsprechenden XML-Writer auf. Diese Methoden werden selten direkt aufgerufen.  
  
## <a name="reading-messages"></a>Lesen von Nachrichten  
 Der einfachste Weg zum Lesen eines Nachrichtentexts besteht im Aufrufen <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. Sie erhalten eine <xref:System.Xml.XmlDictionaryReader> , die Sie verwenden können, um den Nachrichtentext lesen. Beachten Sie, dass die <xref:System.ServiceModel.Channels.Message> in den Zustand "gelesen" übergeht, sobald <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> aufgerufen wird, und wenn Sie nicht den XML-Reader verwenden.  
  
 Die <xref:System.ServiceModel.Channels.Message.GetBody%2A> -Methode können Sie den Zugriff auf den Nachrichtentext als typisiertes Objekt auch. Intern verwendet diese Methode `GetReaderAtBodyContents`, und damit auch die Nachricht in geht die <xref:System.ServiceModel.Channels.MessageState> Status (finden Sie unter der <xref:System.ServiceModel.Channels.Message.State%2A> Eigenschaft).  
  
 Es wird empfohlen, zum Überprüfen der <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> Eigenschaft, in dem Fall der Nachrichtentext leer ist und <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> löst ein <xref:System.InvalidOperationException>. Darüber hinaus ist er eine empfangene Nachricht (z. B. die Antwort), Sie können auch überprüfen möchten <xref:System.ServiceModel.Channels.Message.IsFault%2A>, der angibt, ob die Nachricht einen Fehler enthält.  
  
 Die grundlegendste Überladung von <xref:System.ServiceModel.Channels.Message.GetBody%2A> deserialisiert den Nachrichtentext in eine Instanz eines Typs (angegeben durch den generischen Parameter) unter Verwendung einer <xref:System.Runtime.Serialization.DataContractSerializer> mit den Standardeinstellungen und konfiguriert die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> Kontingent deaktiviert. Wenn Sie ein anderes Serialisierungsmodul verwenden, oder konfigurieren möchten die `DataContractSerializer` in eine nicht standardmäßige Möglichkeit verwenden die <xref:System.ServiceModel.Channels.Message.GetBody%2A> Überladung mit einer <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 Der folgende Code extrahiert beispielsweise Daten aus einem Nachrichtentext, der ein serialisiertes `Person`-Objekt enthält, und gibt den Namen der Person aus.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>Kopieren einer Nachricht in einen Puffer  
 Manchmal ist es erforderlich, mehrmals auf den Nachrichtentext zuzugreifen, beispielsweise um die gleiche Nachricht an mehrere Ziele als Teil eines Verleger-Abonnent-Systems weiterzuleiten. In diesem Fall ist es notwendig, die gesamte Nachricht (einschließlich des Textes) im Arbeitsspeicher zu puffern. Sie erreichen dies durch Aufrufen von <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>. Diese Methode nimmt einen ganzzahligen Parameter an, der die maximale Puffergröße darstellt, und erstellt einen Puffer mit maximal dieser Größe. Legen Sie dafür einen sicheren Wert fest, wenn die Nachricht von einer nicht vertrauenswürdigen Quelle stammt.  
  
 Der Puffer wird zurückgegeben, als eine <xref:System.ServiceModel.Channels.MessageBuffer> Instanz. Es gibt mehrere Möglichkeiten, um auf Daten im Puffer zuzugreifen. Der einfachste Weg besteht im Aufrufen <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> erstellen `Message` Instanzen aus dem Puffer.  
  
 Eine andere Methode Zugriff auf die Daten im Puffer ist das Implementieren der <xref:System.Xml.XPath.IXPathNavigable> Schnittstelle, die <xref:System.ServiceModel.Channels.MessageBuffer> -Klasse implementiert, um das zugrunde liegende XML direkt zugreifen. Einige <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> Überladungen ermöglichen Ihnen die Erstellung <xref:System.Xml.XPath> Navigatoren durch ein Knotenkontingent geschützten Begrenzen der Anzahl von XML-Knoten, die aufgerufen werden können. Dies hilft, Denial-of-Service-Angriffe auf der Grundlage von längerer Verarbeitungszeit zu verhindern. Dieses Kontingent ist standardmäßig deaktiviert. Einige `CreateNavigator` Überladungen können Sie angeben, wie Leerraum in der XML-Code behandelt werden soll mithilfe der <xref:System.Xml.XmlSpace> Enumeration, wobei der Standard `XmlSpace.None`.  
  
 Eine letzte Methode Zugriff auf den Inhalt eines Nachrichtenpuffers ist das Schreiben des Inhalts in einen Stream mit <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>.  
  
 Das folgende Beispiel demonstriert das Arbeiten mit einem `MessageBuffer`: Eine eingehende Nachricht wird an mehrere Empfänger weitergeleitet und anschließend in einer Datei protokolliert. Ohne Pufferung ist dies nicht möglich, da dann der Zugriff auf den Nachrichtentext nur einmal möglich ist.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 Die `MessageBuffer`-Klasse verfügt über andere erwähnenswerte Member. Die <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> Methode kann Ressourcen freigibt, aufgerufen werden, wenn der Pufferinhalt nicht mehr benötigt werden. Die <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> -Eigenschaft gibt die Größe des reservierten Puffers zurück. Die <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> -Eigenschaft gibt den MIME-Inhaltstyp der Nachricht zurück.  
  
## <a name="accessing-the-message-body-for-debugging"></a>Zugreifen auf den Nachrichtentext zum Debuggen  
 Für das Debuggen rufen Sie die <xref:System.ServiceModel.Channels.Message.ToString%2A> Methode, um eine Darstellung der Nachricht als Zeichenfolge abzurufen. Diese Darstellung stimmt im Allgemeinen mit der Darstellung einer Nachricht überein, wenn sie mit dem Textencoder codiert worden wäre, außer dass die XML zur Lesbarkeit besser formatiert wäre. Die einzige Ausnahme ist der Nachrichtentext. Der Text kann nur einmal gelesen werden, und `ToString` ändert den Nachrichtenzustand nicht. Aus diesem Grund die `ToString` Methode möglicherweise nicht auf den Text zuzugreifen und möglicherweise durch einen Platzhalter (z. B. "..." ersetzt oder drei Punkte) ersetzt. Verwenden Sie deswegen `ToString` nicht zum Protokollieren von Nachrichten, wenn der Textinhalt der Nachrichten wichtig ist.  
  
## <a name="accessing-other-message-parts"></a>Zugreifen auf andere Nachrichtenteile  
 Für den Zugriff auf andere Informationen zur Nachricht als den Textinhalt werden verschiedene Eigenschaften bereitgestellt. Diese können jedoch nicht aufgerufen werden, wenn die Nachricht geschlossen wurde:  
  
-   Die <xref:System.ServiceModel.Channels.Message.Headers%2A> Eigenschaft stellt die Nachrichtenheader dar. Weitere Informationen finden Sie im Abschnitt "Arbeiten mit Headern" weiter unten in diesem Thema.  
  
-   Die <xref:System.ServiceModel.Channels.Message.Properties%2A> Eigenschaft darstellt, die Eigenschaften der Nachricht, die Datenelemente benannte an die Nachricht angehängt, die nicht in der Regel ausgegeben, wenn die Nachricht gesendet wird. Weitere Informationen finden Sie im Abschnitt "Arbeiten mit Eigenschaften" weiter unten in diesem Thema.  
  
-   Die <xref:System.ServiceModel.Channels.Message.Version%2A> -Eigenschaft gibt an, die der Nachricht zugeordnete SOAP und WS-Addressing-Version oder `None` wenn SOAP deaktiviert ist.  
  
-   Die <xref:System.ServiceModel.Channels.Message.IsFault%2A> gibt `true` Wenn die Nachricht eine SOAP-Fehlermeldung.  
  
-   Die <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> gibt `true` , wenn die Nachricht leer ist.  
  
 Sie können der <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29> Methode, um ein bestimmtes Attribut im textwrapperelement (z. B. `<soap:Body>`) mit einem bestimmten Namen und Namespace identifiziert. Wenn ein solches Attribut nicht gefunden wurde, wird `null` zurückgegeben. Diese Methode kann nur dann aufgerufen werden, wenn sich die `Message` im Zustand "Erstellt" befindet (wenn noch nicht auf den Nachrichtentext zugegriffen wurde).  
  
## <a name="working-with-headers"></a>Arbeiten mit Headern  
 Ein `Message` kann eine beliebige Anzahl benannter XML-Fragmente bezeichnet enthalten *Header*. Jedes Fragment wird normalerweise einem SOAP-Header zugeordnet. Header erfolgt über die `Headers` Eigenschaft vom Typ <xref:System.ServiceModel.Channels.MessageHeaders>. <xref:System.ServiceModel.Channels.MessageHeaders> ist eine Sammlung von <xref:System.ServiceModel.Channels.MessageHeaderInfo> Objekte und auf einzelne Header können über zugegriffen werden die <xref:System.Collections.IEnumerable> Schnittstelle oder durch den Indexer. Im folgenden Code werden z. B. die Namen aller Header in einer `Message` aufgelistet.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>Hinzufügen, Entfernen und Suchen von Headern  
 Sie können einen neuen Header hinzuzufügen, am Ende aller vorhandenen Header mit den <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A> Methode. Sie können die <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A> Methode, um einen Header an einem bestimmten Index einzufügen. Vorhandene Header werden für das eingefügte Element verschoben. Header werden nach ihrem Index geordnet, dabei ist der erste verfügbare Index 0. Sie können mithilfe der verschiedenen <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> überladene Methoden zum Hinzufügen von Headern aus einer anderen `Message` oder `MessageHeaders` Instanz. Einige Überladungen kopieren einen einzelnen Header, während andere alle Header kopieren. Die <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> -Methode entfernt alle Header. Die <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> -Methode entfernt einen Header an einem bestimmten Index (alle nachfolgenden Header dahinter). Die <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> -Methode entfernt alle Header mit einem bestimmten Namen und Namespace.  
  
 Abrufen einer bestimmten Headers mit dem <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A> Methode. Diese Methode nimmt den Namen und Namespace des zu suchenden Headers an, und gibt seinen Index zurück. Wenn der Header mehrmals auftritt, wird eine Ausnahme ausgelöst. Wenn der Header nicht gefunden wurde, wird -1 zurückgegeben.  
  
 Im SOAP-Headermodell können Header einen `Actor`-Wert aufweisen, der den gewünschten Empfänger des Headers angibt. Die grundlegendste `FindHeader`-Überladung sucht nur Header, die für den letzten Empfänger der Nachricht vorgesehen sind. Mit einer anderen Überladung können Sie jedoch angeben, welche `Actor`-Werte in der Suche enthalten sind. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] zur SOAP-Spezifikation.  
  
 Ein [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> Methode dient zum Kopieren von Headern aus einer <xref:System.ServiceModel.Channels.MessageHeaders> Auflistung in ein Array von <xref:System.ServiceModel.Channels.MessageHeaderInfo> Objekte.  
  
 Sie können für den Zugriff auf die XML-Daten in einem Header, Aufrufen <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> und einen XML-Leser für den Headerindex zurückgeben. Wenn Sie den Inhalt des Headers in ein Objekt zu deserialisieren möchten, verwenden <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> oder eine der anderen Überladungen. Die grundlegendsten Überladungen Deserialisieren Header mit der <xref:System.Runtime.Serialization.DataContractSerializer> konfiguriert, die in der Standard-Methode. Wenn Sie ein anderes Serialisierungsprogramm oder eine andere Konfiguration von `DataContractSerializer` verwenden möchten, nutzen Sie eine der Überladungen, die ein `XmlObjectSerializer` akzeptieren. Einige Überladungen akzeptieren auch den Headernamen, Namespace und optional eine Liste von `Actor`-Werte anstelle eines Index; dies ist eine Kombination von `FindHeader` und `GetHeader`.  
  
## <a name="working-with-properties"></a>Arbeiten mit Eigenschaften  
 Eine `Message`-Instanz kann eine beliebige Anzahl von benannten Objekten beliebiger Typen enthalten. Auf diese Auflistung wird über die `Properties`-Eigenschaft vom Typ `MessageProperties` zugegriffen. Die Auflistung implementiert die <xref:System.Collections.Generic.IDictionary%602> -Schnittstelle und fungiert als Zuordnung von <xref:System.String> auf <xref:System.Object>.\</TKey, TValue> Eigenschaftswerte nicht direkt an einen beliebigen Teil der Nachricht zuordnen normalerweise bieten vielmehr verschiedene nachrichtenverarbeitungshinweise für die Kanäle in der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Kanalstapel oder die [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> dienstframework. Ein Beispiel finden Sie unter [Data Transfer Architectural Overview](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
## <a name="inheriting-from-the-message-class"></a>Erben von der Meldungsklasse  
 Erstellen Sie eine von der `CreateMessage`-Klasse abgeleitete Klasse, wenn die mit `Message` erstellten integrierten Nachrichtentypen nicht den Anforderungen entsprechen.  
  
### <a name="defining-the-message-body-contents"></a>Definieren des Nachrichtentextinhalts  
 Für den Zugriff auf Daten innerhalb eines Nachrichtentexts gibt es drei grundlegende Verfahren: Schreiben, Lesen und Kopieren in einen Puffer. Diese Vorgänge letztlich in die <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A>, und <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> Methoden, die aufgerufen wird, bzw. in einer abgeleiteten Klasse von `Message`. Die `Message`-Basisklasse stellt sicher, dass für jede `Message`-Instanz nur eine dieser Methoden aufgerufen wird und dieser Vorgang jeweils nur einmal stattfindet. Die Basisklasse stellt auch sicher, dass die Methoden nicht für eine geschlossene Nachricht aufgerufen werden. Es ist nicht erforderlich, den Nachrichtenzustand in der Implementierung zu verfolgen.  
  
 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> ist eine abstrakte Methode und muss implementiert werden. Die grundlegendste Weise zum Definieren des Textinhalts der Nachricht ist, mit dieser Methode zu schreiben. Zum Beispiel enthält die folgende Nachricht 100.000 Zufallszahlen von 1 bis 20.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 Die `OnGetReaderAtBodyContents`-Methode und die `OnCreateBufferedCopy`-Methode verfügen über Standardimplementierungen, die in den meisten Fällen funktionieren. Die Standardimplementierungen rufen `OnWriteBodyContents` auf, speichern die Ergebnisse im Puffer und arbeiten mit dem resultierenden Puffer. In einigen Fällen genügt dies möglicherweise nicht. In vorhergehenden Beispiel führt das Lesen der Nachricht dazu, dass 100.000 XML-Elemente im Puffer gespeichert werden, was unter Umständen nicht wünschenswert ist. Es kann empfehlenswert sein, `OnGetReaderAtBodyContents` zu überschreiben, um eine benutzerdefinierte abgeleitete `XmlDictionaryReader`Klasse zurückzugeben, die Zufallszahlen bereitstellt. Sie können dann `OnWriteBodyContents` überschreiben, um den von der `OnGetReaderAtBodyContents`-Eigenschaft zurückgegebenen Leser zu verwenden, wie im folgenden Beispiel dargestellt.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 Auf ähnliche Weise können Sie `OnCreateBufferedCopy` überschreiben, um eine eigene abgeleitete `MessageBuffer`-Klasse zurückzugeben.  
  
 Zusätzlich zum Bereitstellen von Nachrichtentextinhalt muss die abgeleitete Nachrichtenklasse auch die `Version`-Eigenschaft, die `Headers`-Eigenschaft und die `Properties`-Eigenschaft überschreiben.  
  
 Beachten Sie, dass beim Erstellen der Kopie einer Nachricht die Kopie die Nachrichtenheader aus dem Original verwendet.  
  
### <a name="other-members-that-can-be-overridden"></a>Andere Member, die überschrieben werden können  
 Sie können außer Kraft setzen der <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, und <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A> Methoden, um anzugeben, wie die SOAP-Umschlag, SOAP-Header und SOAP-Textelement-Starttags geschrieben werden. Diese entsprechen normalerweise `<soap:Envelope>``<soap:Body>`, `<soap:Header>` und . Diese Methoden sollten normalerweise nichts schreiben, wenn die `Version`-Eigenschaft `MessageVersion.None` zurückgibt.  
  
> [!NOTE]
>  Die Standardimplementierung von `OnGetReaderAtBodyContents` ruft `OnWriteStartEnvelope` und `OnWriteStartBody` auf, bevor `OnWriteBodyContents` aufgerufen wird und die Ergebnisse im Puffer gespeichert werden. Header werden nicht geschrieben.  
  
 Überschreiben Sie die <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A> Methode, um die gesamte Nachricht erstellt wird, wie aus den verschiedenen Teilen ändern. Die `OnWriteMessage` aufgerufen, aus <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> und aus der <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> Implementierung. Beachten Sie, dass das Überschreiben <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> wird nicht empfohlen. Es ist besser, überschreiben Sie die entsprechende `On` Methoden (z. B. <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, und <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>.  
  
 Überschreiben Sie <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A> überschreiben, wie der Nachrichtentext während des Debuggens dargestellt wird. Der Standard ist die Darstellung als drei Punkte ("…"). Diese Methode kann mehrfach ausgerufen werden, wenn der Nachrichtenzustand nicht "Geschlossen" lautet. Eine Implementierung dieser Methode sollte nie eine Aktion verursachen, die nur einmal ausgeführt werden muss (wie das Lesen eines Vorwärtsstreams).  
  
 Überschreiben Sie die <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A> Methode, um den Zugriff auf Attribute im SOAP-Textelement zuzulassen. Diese Methode kann beliebig oft aufgerufen werden, der `Message`-Basistyp stellt jedoch sicher, dass sie nur dann aufgerufen wird, wenn der Zustand der Nachricht "Erstellt" lautet. Es ist nicht erforderlich, den Zustand in einer Implementierung zu überprüfen. Die Standardimplementierung gibt immer `null` zurück, was bedeutet, dass im Textelement keine Attribute vorhanden sind.  
  
 Wenn Ihre `Message` -Objekt eine spezielle Bereinigung ausführen, wenn der Nachrichtentext nicht mehr benötigt wird, können Sie überschreiben <xref:System.ServiceModel.Channels.Message.OnClose%2A>. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Die `IsEmpty`-Eigenschaft und die `IsFault`-Eigenschaft können überschrieben werden. Standardmäßig geben beide `false` zurück.