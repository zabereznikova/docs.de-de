---
title: Datentransformationen
description: Untersuchen Sie die in ML.NET unterstützten herausragenden technischen Komponenten.
author: natke
ms.author: nakersha
ms.date: 04/02/2019
ms.openlocfilehash: d3261f88a8e52c71f8ddf4d3d5c90b2e2b22b620
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64636548"
---
# <a name="data-transformations"></a>Datentransformationen

Datentransformationen dienen zur Vorbereitung von Daten für das Trainieren des Modells. Die Transformationen in diesem Handbuch geben Klassen zurück, die die [IEstimator](xref:Microsoft.ML.IEstimator`1)-Schnittstelle implementieren. Datentransformationen können miteinander verkettet werden. Jede Transformation erwartet und erzeugt Daten bestimmter Typen und Formate, die in der verknüpften Referenzdokumentation angegeben werden.

Einige Datentransformationen erfordern Trainingsdaten, um ihre Parameter zu berechnen. Beispiel: Der <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A>-Transformator berechnet den Mittelwert und die Varianz der Trainingsdaten während des `Fit()`-Vorgangs und verwendet diese Parameter im `Transform()`-Vorgang. 

Andere Datentransformationen erfordern keine Trainingsdaten. Beispiel: Die <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*>-Transformation kann die `Transform()`-Operation durchführen, ohne während der `Fit()`-Operation Trainingsdaten gesehen zu haben.

## <a name="column-mapping-and-grouping"></a>Zuordnung und Gruppierung von Spalten

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | Verketten einer oder mehrerer Eingabespalten in einer neuen Ausgabespalte |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | Kopieren und Umbenennen einer oder mehrerer Eingabespalten |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | Löschen einer oder mehrerer Eingabespalten |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | Auswählen einer oder mehrerer beizubehaltender Spalten aus den Eingabedaten |

## <a name="normalization-and-scaling"></a>Normalisierung und Skalierung

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | Subtrahieren des Mittelwerts (der Trainingsdaten) und Dividieren durch die Varianz (der Trainingsdaten) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | Normalisieren auf Basis des Logarithmus der Trainingsdaten |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | Skalieren von Eingabevektoren durch ihre [LP-Norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), wobei P gleich 1, 2 oder unendlich ist. Der Standardwert ist die L2-Norm (Euklidischer Abstand) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | Skalieren jedes Werts in einer Zeile durch Subtrahieren des Mittelwerts der Zeilendaten und Division entweder durch die Standardabweichung oder die L2-Norm (der Daten aus der Zeile) und Multiplizieren mit einem konfigurierbaren Skalierungsfaktor (Standard: 2) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | Zuweisen des Eingabewerts zu einem Binindex und Division durch die Anzahl der Bins, um einen Gleitkommawert zwischen 0 und 1 zu erzeugen. Die Bingrenzen werden berechnet, um die Trainingsdaten gleichmäßig auf Bins zu verteilen |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | Zuweisen des Eingabewerts zu einem Bin basierend auf seiner Korrelation mit der Bezeichnungsspalte |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | Skalieren der Eingabe um den Unterschied zwischen den minimalen und maximalen Werten in den Trainingsdaten |

## <a name="conversions-between-data-types"></a>Konvertierungen zwischen Datentypen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | Konvertieren des Typs einer Eingabespalte in einen neuen Typ |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue*> | Zuordnen von Werten zu Schlüsseln (Kategorien) auf Grundlage des angegebenen Zuordnungenwörterbuchs |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*> | Zuordnen von Werten zu Schlüsseln (Kategorien) durch Erstellen der Zuordnung aus den Eingabedaten |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue*> | Konvertieren von Schlüsseln zurück in ihre ursprünglichen Werte |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector*> | Konvertieren von Schlüsseln zurück in Vektoren ursprünglicher Werte |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector*> | Konvertieren von Schlüsseln zurück in einen binären Vektor ursprünglicher Werte |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash*> | Anwenden des Hashalgorithmus auf den Wert in der Eingabespalte |

## <a name="text-transformations"></a>Texttransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText*> | Umwandeln einer Textspalte in ein Gleitkommaarray der normalisierten Anzahl von N-Grammen und Char-Grammen | 
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords*> | Aufteilen einer oder mehrerer Textspalten in einzelne Wörter |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys*> | Aufteilen einer oder mehrerer Textspalten in einzelne Zeichengleitkommazahlen über eine Reihe von Themen |
| <xref:Microsoft.ML.TextCatalog.NormalizeText*> | Ändern von Groß-/Kleinschreibung, Entfernen von diakritischen Zeichen, Satzzeichen und Zahlen |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams*> | Umwandeln einer Textspalte in eine Sammlung mit der Anzahl der N-Gramme (Abfolgen aufeinander folgender Wörter)|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags*> | Umwandeln einer Textspalte in einen Vektor der Sammlung mit der Anzahl der N-Gramme |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams*> | Umwandeln einer Textspalte in einen Vektor der Anzahl von N-Grammen, für die der Hashwert berechnet wurde |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags*> | Umwandeln einer Textspalte in eine Sammlung der Anzahl von N-Grammen, für die der Hashwert berechnet wurde |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords*>  | Entfernen der Standardstoppwörter für die angegebene Sprache aus Eingabespalten |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords*> | Entfernt die angegebenen Stoppwörter aus Eingabespalten |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation*> | Umwandeln eines Dokuments (dargestellt als Vektor von Gleitkommazahlen) in einen Vektor von Gleitkommazahlen über eine Reihe von Themen |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding*> | Konvertieren von Vektoren von Texttoken in Satzvektoren mithilfe eines vortrainierten Modells |

## <a name="image-transformations"></a>Bildtransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> | Konvertieren eines Bilds in Graustufen |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage*> | Konvertieren eines Vektors von Pixeln in <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*> | Konvertieren von Pixeln eines Eingabebilds in einen Vektor aus Zahlen |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*> | Laden von Bildern aus einem Ordner in den Arbeitsspeicher |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*> | Ändern der Größe von Bildern |

## <a name="categorical-data-transformations"></a>Kategorische Datentransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*> | Konvertieren einer oder mehrerer Textspalten in mit [1-aus-n-Code](https://en.wikipedia.org/wiki/One-hot) codierte Vektoren |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding*> | Konvertieren einer oder mehrerer Textspalten in hashbasierte mit 1-aus-n-Code codierte Vektoren |

## <a name="missing-values"></a>Fehlende Werte

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues*> | Erstellen einer neuen booleschen Ausgabespalte, deren Wert „true“ ist, wenn der Wert in der Eingabespalte fehlt |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*> | Erstellen einer neuen Ausgabespalte, deren Wert auf einen Standardwert festgelegt ist, wenn der Wert aus der Eingabespalte nicht vorhanden ist, und andernfalls auf den Eingabewert |

## <a name="feature-selection"></a>Featureauswahl

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount*> | Auswählen von Features, deren nicht standardmäßige Werte größer als der Schwellenwert sind |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation*> | Wählen Sie die Features aus, von denen die Daten in der Bezeichnungsspalte am meisten abhängen |

## <a name="custom-transformations"></a>Benutzerdefinierte Transformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping*> | Transformieren vorhandener Spalten in neue mit einer benutzerdefinierten Zuordnung |
