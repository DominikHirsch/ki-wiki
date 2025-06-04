---
layout: default
title: Prompt Engineering
nav_order: 1
---

# Prompt Engineering

## 1. Einführung

Ein **Prompt** ist eine Eingabe oder Anweisung, die ein Nutzer:innen einer KI (insbesondere LLMs – Large Language Models) gibt, um eine bestimmte Antwort oder ein bestimmtes Verhalten zu erzeugen. Im Bildungsbereich spielt Prompt Engineering eine Schlüsselrolle, da gut gestaltete Prompts die Qualität und Relevanz der KI-Ausgaben maßgeblich beeinflussen.

Hallo Sarah. Jetzt hier aber.

---

## 2. Aufbau und Bestandteile eines Prompts

1. **System-/Kontext-Information**  
   - Beschreibt der KI ihre Rolle oder den Kontext (z. B. "Du bist ein Nachhilfelehrer in Mathematik").

2. **Aufgabenanweisung**  
   - Formuliert konkret, was die KI tun soll (z. B. "Erkläre das Konzept der quadratischen Gleichung in einfachen Worten").

3. **Beispielhafte Ein- und Ausgaben (Few-Shot-Ansatz)**  
   - Liste von Beispiel-Paaren (Input → Output), um der KI zu zeigen, wie sie antworten soll.

4. **Parameter und Einschränkungen**  
   - Länge der Antwort, Stilvorgaben, Format (z. B. "Fasse in maximal 150 Wörtern zusammen").

---

## 3. Einfluss von Prompts auf KI-Outputs

| **Prompt-Formulierung**           | **Ergebnischarakteristik**                           |
|-----------------------------------|-----------------------------------------------------|
| Sehr allgemein: "Erkläre Algebra" | Grober Überblick, ggf. nicht zielgruppenspezifisch. |
| Spezifiziert: "Erkläre Algebra für 10-jährige" | Einfach gehalten, altersgerecht.                    |
| Few-Shot-Beispiel mit Formatvorgabe   | Konsistente Antwortstruktur, klare Formatierung.     |

**Grafik (ASCII-Diagramm)**  
┌────────────────────┐  
│ General Prompt │  
│ (z. B. "Erkläre X") │  
└─────────┬──────────┘  
↓  
↘──────────────↙  
┌─────────┴────────┐  
│ Spezifischer Prompt │  
│ (z. B. "Erkläre X │  
│ für Zielgruppe Y") │  
└─────────┬────────┘  
↓  
┌─────────────────┐  
│ Few-Shot / Beispiele │  
│ (Input→Output-Paare) │  
└─────────────────┘


---

## 4. Best Practices für effektives Prompting im Bildungskontext

1. **Klarheit & Präzision**  
   - Vermeide Mehrdeutigkeiten. Gib genaue Anweisungen, z. B. "Erkläre den Unterschied zwischen arithmetischem und geometrischem Mittel."

2. **Kontextualisierung**  
   - Stelle den Hintergrund bereit. Beispiel: "In einer 9. Klasse, Kapitel Bruchrechnung…"

3. **Iteratives Vorgehen**  
   - Teste und verfeinere Prompts schrittweise.  
   - Arbeite nach dem **Plan-Do-Check-Act (PDCA)-Prinzip**:  
     1. Plan: Prompt entwerfen  
     2. Do: Prompt in die KI eingeben  
     3. Check: Ergebnis evaluieren  
     4. Act: Prompt anpassen  

4. **Few-Shot- oder Chain-of-Thought-Techniken**  
   - **Few-Shot:** Zeige der KI Beispiele (Input→Output).  
   - **Chain of Thought:** Fordere die KI auf, Zwischenschritte offline zu notieren ("Denke Schritt für Schritt...").

5. **Rollen- und Stilvorgaben**  
   - Gib der KI eine Rolle (z. B. "Du bist ein erfahrener Mathematiklehrer, der in einfachen Worten erklärt.").  
   - Definiere stilistische Vorgaben: formell/informell, komplex/einfach.

---

## 5. Techniken im Überblick

| **Technik**            | **Beschreibung**                                                                                  | **Anwendungsbeispiel**                                   |
|------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------|
| Zero-Shot              | Prompt ohne Beispiele, KI muss direkt basierend auf allgemeinem Wissen antworten.                 | "Erkläre den Satz des Pythagoras."                         |
| Few-Shot               | Prompt enthält Beispiel-Paare (Input→Output), um das gewünschte Format zu veranschaulichen.       | "Frage: 2+2? Antwort: 4. Frage: 5*3? Antwort: 15. Frage: ..." |
| Chain-of-Thought       | KI wird angeleitet, den Denkprozess in Schritten darzustellen.                                      | "Erkläre Schritt für Schritt, wie man 7/3 dividiert."       |
| Prompt-Tuning          | Feintuning von LLMs auf spezifische Aufgaben mit zusätzlichen Trainingsdaten.                     | Anpassung eines Modells auf fachspezifische Fragen.         |
| Reinforcement Learning | KI lernt durch Belohnung/Strafe, Prompts werden im Training belohnt, wenn sie bessere Outputs liefern. | Optimierung von Tutor-Antworten über Nutzungsfeedback.      |

---

## 6. Qualitätsmessung von Prompts

- **Relevanz**  
  → Metrik: Prozentuale Übereinstimmung mit pädagogischen Lernzielen.  
- **Genauigkeit**  
  → Metrik: Anzahl korrekter Faktenformulierungen / Gesamtaussage.  
- **Vollständigkeit**  
  → Metrik: Abdeckung aller geforderten Unterpunkte (z. B. in einer Checkliste abhaken).  
- **Kohärenz**  
  → Metrik: Lesbarkeitsindex (z. B. Flesch-Wert) oder Expertenbewertungen.  
- **Kreativität**  
  → Metrik: Innovationsindex (subjektiv durch Lehrkräfte oder Peer-Review).  

**Beispiel für eine Bewertungsmatrix:**

| **Kriterium**   | **Metrik**                         | **Skala (1–5)** | **Definition (Beispiel)**                              |
|-----------------|------------------------------------|-----------------|---------------------------------------------------------|
| Relevanz        | % Übereinstimmung mit Lernzielen   | 1 = <50 %, 5 = >90 %    | Wie gut passt die Antwort zu den Lehrzielen?             |
| Genauigkeit     | Anzahl korrekter Fakten / Gesamt   | 1 = <70 %, 5 = >95 %    | Anteil faktisch korrekter Aussagen                       |
| Vollständigkeit | Abgedeckte Unterpunkte / Gesamt     | 1 = <50 %, 5 = 100 %    | Wurden alle geforderten Aspekte beantwortet?            |
| Kohärenz        | Flesch-Lesbarkeitsindex            | 1 = <30, 5 = >70       | Wie verständlich und logisch ist der Text?                |
| Kreativität     | Expertenbewertung                  | 1 = wenig, 5 = sehr viel | Wie originell und abwechslungsreich ist die Antwort?     |

---

## 7. Anwendungsbeispiele im Bildungsbereich

1. **Mathematik-Tutor**  
   - **Prompt:** „Du bist ein Mathetutor für 7. Klasse. Erkläre, wie man lineare Gleichungen löst, mit Beispielen.“  
   - **Output:** Schritt-für-Schritt-Anleitung mit Beispielaufgaben, detailliert und schülergerecht.

2. **Sprach-Übersetzer für Mehrsprachigkeitsklassen**  
   - **Prompt:** „Übersetze folgenden Text in einfachem Deutsch und erkläre den Inhalt instruierend für Deutschlernende.“  
   - **Output:** Einfache Übersetzung plus erläuternde Fußnoten.

3. **Wissenschaftliche Artikel zusammenfassen**  
   - **Prompt:** „Fasse diesen Artikel in max. 200 Wörtern zusammen, hebe zentrale Argumente und Methoden hervor.“  
   - **Output:** Prägnante Zusammenfassung mit Unterteilung in Einleitung, Methode, Ergebnisse, Fazit.

---

## 8. Zusammenfassung

- **Prompt Engineering** ist die Kunst, KI-Systeme durch gezielte Eingaben zu steuern.  
- **Qualität** hängt ab von Klarheit, Kontext, Beispielen und iterativer Verfeinerung.  
- **Best Practices** im Bildungskontext betonen Anpassung an Zielgruppe, klare Rollen- und Formatvorgaben, sowie Evaluation.  
- **Ziel** ist, dass KI als unterstützendes Werkzeug Lehr-Lern-Prozesse bereichert, ohne menschliche Kontrolle und kritisches Denken zu ersetzen.

---

## 9. Weiterführende Ressourcen

- **Arxiv-Artikel**: „A Survey on Prompt Engineering Techniques for Large Language Models“ ([arxiv.org/abs/2305.04689](https://arxiv.org/abs/2305.04689))  
- **Praxisleitfaden**: „Effektives Prompt-Engineering für Lehrkräfte“ (OER-Material, 2024)  
- **Online-Tool**: PromptBase (Marktplatz für optimierte Prompts)  
- **Buch**: „Prompt Engineering – Die Kunst der KI-Kommunikation“ (2023)

