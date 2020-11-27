---
title: Dienstframeworkdaten
ms.date: 03/30/2017
ms.assetid: 2a2c8ddc-4e82-4e7f-a79f-97085c469517
ms.openlocfilehash: 8bb6e9df6a77eda5875981a0bf7783f50671a589
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255779"
---
# <a name="service-framework-data"></a>Dienstframeworkdaten

In diesem Thema sind alle von Dienstframeworkdaten erzeugten Ausnahmen aufgeführt.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|AddressingExtensionInBadNS|Das angegebene Element im angegebenen Namespace ist nicht gültig. Dies bedeutet, dass es sich beim angegebenen Element um ein doppeltes Element oder um eine ungültige Erweiterung handelt, da Erweiterungselemente nicht im Adressierungsnamespace vorhanden sein können.|  
|BinaryEncoderSessionInvalid|Die binäre Encodersitzung ist ungültig, da ein Fehler bei der Decodierung einer vorherigen Nachricht aufgetreten ist.|  
|CannotDetectAddressingVersion|Kann keine WS-Adressierungsversion erkennen. EndpointAddress beginnt nicht mit einem Element.|  
|CouldNotFindNamespaceForPrefix|Das angegebene Präfix verfügt über keine Namespacebindung im Gültigkeitsbereich.|  
|EncoderBadContentType|Verarbeitung zu contentType nicht möglich.|  
|EncoderEnvelopeVersionMismatch|Die Umschlagversion der angegebenen eingehenden Nachricht passt nicht zum angegebenen Encoder. Stellen Sie sicher, dass die Bindung mit der gleichen Version wie die erwarteten Nachrichten konfiguriert wird.|  
|EncoderMessageVersionMismatch|Die Nachrichtenversion der angegebenen ausgehenden Nachricht passt nicht zum angegebenen Encoder. Stellen Sie sicher, dass die Bindung mit der gleichen Version wie die Nachricht konfiguriert wird.|  
|ExtraContentIsPresentInFaultDetail|Zusätzlicher XML-Inhalt (Extensible Markup Language) ist im Fehlerdetailelement vorhanden. Nur ein Element wird zugelassen.|  
|FilterBadTableType|Die für einen Filter erstellte IMessageFilterTable kann keine MessageFilterTable sein oder sich von MessageFilterTable herleiten.|  
|FilterTableInvalidForLookup|Der MessageFilterTable-Zustand ist fehlerhaft. Die angeforderte Suche kann nicht ausgeführt werden.|  
|MandatoryHeaderNotUnderstood|Ein oder mehrere erforderliche, einfache Objektzugangsprotokollheaderblöcke wurden nicht verstanden.|  
|MessageBodyIsStream|Der Nachrichtentext ist ein Stream.|  
|MessageBodyIsUnknown|Das Format des Nachrichtentexts ist unbekannt.|  
|MessageBodyReaderInvalidReadState|Der angegebene ReadState des Nachrichtentextreaders kann nicht verwendet werden.|  
|MessageTextEncodingNotSupported|Die angegebene Textcodierung, die im Textnachrichtenformat eingesetzt wird, wird nicht unterstützt.|  
|MissingMessageID|Der Anforderungsnachricht fehlt ein MessageID-Header. Ein MessageID-Header ist erforderlich, um eine Antwort zu korrelieren.|  
|MultipleMessageHeaders|Mehr als ein Header mit dem angegebenen Namen und Namespace wurde gefunden.|  
|MultipleMessageHeadersWithActor|Mehr als ein Header mit dem angegebenen Namen, Namespace und Rolle wurde gefunden.|  
|MultipleRelatesToHeaders|Mehr als ein RelatesTo-Header mit der angegebenen Beziehung wurde gefunden. Nur einer wird für jede Beziehung zugelassen.|  
|QueryFunctionTypeNotSupported|Der angegebene Rückgabetyp für IXsltContextFunction wird nicht unterstützt.|  
|QueryIteratorOutOfScope|Der XPathNodeIterator ist ungültig geworden. XPathNodeIterators, die als Argumente an IXsltContextFunctions übergeben werden, sind nur innerhalb der Funktion gültig. Sie können nicht zur späteren Verwendung zwischengespeichert oder durch die Funktion zurückgegeben werden.|  
|QueryVariableNull|IXsltContextVariable-Methoden können keine NULL zurückgeben.|  
|QueryVariableTypeNotSupported|Der angegebene, von IxsltContextVariable abgeleitete Typ wird nicht unterstützt.|  
|ReceiveShutdownReturnedMessage|Der Kanal hat eine unerwartete Eingabenachricht mit der angegebenen Aktion empfangen, während er geschlossen wurde. Schließen Sie den Kanal, wenn Sie keine Eingabenachrichten mehr erwarten.|  
|XmlBufferInInvalidState|Ein interner Fehler ist aufgetreten. Der Vorgang kann aufgrund des XML-Pufferstatus nicht durchgeführt werden.|  
|XmlBufferQuotaExceeded|Die Größe, die notwendig ist, um den XML-Inhalt (Extensible Markup Language) zu puffern, hat das Pufferkontingent überschritten.|
