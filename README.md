# guia-retinografia
import React, { useState } from 'react';

// Main App component
const App = () => {
  // Helper component to render content blocks
  const Section = ({ title, children, imageUrl, imageAlt }) => (
    <div className="bg-white p-6 rounded-lg shadow-md mb-8">
      <h2 className="text-2xl md:text-3xl font-bold text-gray-800 mb-4 border-b-2 border-indigo-500 pb-2">
        {title}
      </h2>
      {imageUrl && (
        <div className="mb-4 text-center">
          <img
            src={imageUrl}
            alt={imageAlt}
            className="rounded-lg shadow-md max-w-full h-auto mx-auto"
            onError={(e) => { e.target.onerror = null; e.target.src = 'https://placehold.co/600x300/CCCCCC/FFFFFF?text=Imagem+Nao+Disponivel'; }} // Fallback image
          />
          <p className="text-sm text-gray-500 mt-2">{imageAlt}</p>
        </div>
      )}
      <div className="text-gray-700 leading-relaxed">
        {children}
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-100 to-purple-100 font-sans p-4 sm:p-8">
      {/* Header Section */}
      <header className="text-center mb-10">
        <h1 className="text-4xl md:text-5xl font-extrabold text-indigo-800 leading-tight">
          Retinografia: Guia Completo de Avaliação do Fundo de Olho
        </h1>
        <p className="mt-4 text-lg text-indigo-700">
          Uma visão geral sobre a retinografia e os seus princípios.
        </p>
      </header>

      {/* Main Content Area */}
      <main className="max-w-4xl mx-auto">
        <Section
          title="Visão Geral da Retinografia"
          imageUrl="https://placehold.co/600x300/4F46E5/FFFFFF?text=Fundo+de+Olho+Normal"
          imageAlt="[Imagem de um fundo de olho normal visto através de uma retinografia]"
        >
          <p className="mb-4">
            A retinografia é um exame oftalmológico que consiste na documentação fotográfica do fundo de olho, permitindo a visualização e análise de estruturas como a retina, o nervo óptico, a mácula e os vasos sanguíneos retinianos. É uma ferramenta essencial para o acompanhamento de diversas condições oculares.
          </p>
          <p className="mb-4">
            As suas principais indicações clínicas incluem:
          </p>
          <ul className="list-disc pl-5 space-y-2">
            <li>Rastreamento e acompanhamento de retinopatia diabética.</li>
            <li>Monitorização do glaucoma.</li>
            <li>Avaliação da degeneração macular relacionada à idade (DMRI).</li>
            <li>Identificação de alterações em pacientes com hipertensão arterial sistémica.</li>
            <li>Diagnóstico e acompanhamento de neurorretinopatias.</li>
            <li>Uso em tele-oftalmologia para avaliação remota.</li>
          </ul>
          <p className="mb-4">
            É fundamental compreender os princípios ópticos da câmara de fundo e as principais modalidades (cor, red-free, autofluorescência, angiografias com fluoresceína e indocianina, ultra-widefield, estereoscopia) para assegurar uma análise fiável.
          </p>
          <p className="mb-4">
            Padronizar critérios de qualidade das imagens (centralização, foco, exposição, campo, ausência de artefatos) é crucial. Recomenda-se empregar um checklist sistemático que evite omissões: qualidade → orientação → disco óptico → vasos → mácula → retina média → periferia. Além disso, é importante correlacionar achados estruturais com dados funcionais (campo visual), estruturais 3-D (OCT) e histórico evolutivo do paciente.
          </p>
        </Section>

        <Section
          title="Pontos-chave"
          imageUrl="https://placehold.co/600x300/8B5CF6/FFFFFF?text=Retina+com+Marcacoes"
          imageAlt="[Imagem de uma retinografia com marcações indicando as áreas de avaliação]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>A foto colorida padrão cobre 30-50°; lentes wide-field alcançam até 140° do polo posterior.</li>
            <li>A imagem **red-free** (filtro verde 540-570 nm) realça vasos, hemorragias e defeitos da camada de fibras nervosas (RNFL).</li>
            <li>Anote sempre: olho (OD/OS), data, midríase ou não, qualidade e tipo de filtro/flash. A ausência de metadados invalida a documentação.</li>
            <li>Avalie o disco óptico pelo local da deflexão vascular (não apenas pela cor) e relacione a escavação/disco (C/D); assimetria {'>'} 0,2 ou C/D {'>'} 0,6 impõem alerta para glaucoma.</li>
            <li>A relação artéria:veia ≈ 2:3 (ou 0,66) — estreitamento arteriolar e AV-nicking sugerem hipertensão sistémica.</li>
            <li>**RNFL**: Bandas hiporreflectivas (defeitos em cunha) no filtro verde são preditores precoces de dano axonal.</li>
          </ul>
        </Section>

        <Section
          title="Princípios e Modalidades da Retinografia"
          imageUrl="https://placehold.co/600x300/EC4899/FFFFFF?text=Tipos+de+Retinografia"
          imageAlt="[Imagem ilustrativa dos diferentes modos de retinografia]"
        >
          <p className="mb-4">
            A óptica da retinografia é baseada em oftalmoscopia indireta monocular, com um sistema de iluminação anular que evita reflexos corneanos.
          </p>
          <h3 className="text-xl font-bold text-gray-800 mb-2">Modos principais:</h3>
          <ul className="list-disc pl-5 space-y-2">
            <li>
              <strong className="text-purple-600">Color</strong>: Avaliação global de retina, vasos, mácula e disco.
            </li>
            <li>
              <strong className="text-purple-600">Red-free</strong>: Filtro verde que destaca hemorragias, exsudatos e defeitos da RNFL.
            </li>
            <li>
              <strong className="text-purple-600">Fundus autofluorescência</strong>: Mapeia depósito de lipofuscina no epitélio pigmentar da retina (EPR).
            </li>
            <li>
              <strong className="text-purple-600">Fluorescein Angiography</strong>: Avalia a vascularização retiniana dinâmica (útil em doenças isquémicas).
            </li>
            <li>
              <strong className="text-purple-600">ICG Angiography</strong>: Detalha a circulação coroidal (ex.: lesões polipoidais).
            </li>
            <li>
              <strong className="text-purple-600">Ultra-widefield (UWFS)</strong>: Captura até 200°; útil na periferia, em diabéticos e distrofias.
            </li>
            <li>
              <strong className="text-purple-600">Estereoscopia digital</strong>: Dois ângulos simultâneos geram visão 3-D de relevo papilar e neovasos.
            </li>
          </ul>
        </Section>

        <Section
          title="Preparação e Controle de Qualidade"
          imageUrl="https://placehold.co/600x300/10B981/FFFFFF?text=Preparo+do+Paciente"
          imageAlt="[Imagem de um paciente sendo preparado para uma retinografia]"
        >
          <h3 className="text-xl font-bold text-gray-800 mb-2">Paciente:</h3>
          <ul className="list-disc pl-5 space-y-2 mb-4">
            <li>Explicar a necessidade do flash.</li>
            <li>Obter consentimento.</li>
            <li>Idealmente, realizar midríase farmacológica (tropicamida ± fenilefrina), exceto com câmaras não-midriáticas.</li>
          </ul>
          <h3 className="text-xl font-bold text-gray-800 mb-2">Posicionamento:</h3>
          <ul className="list-disc pl-5 space-y-2 mb-4">
            <li>Queixo no suporte, testa contra a barra.</li>
            <li>Fixação central ou periférica conforme o campo desejado.</li>
          </ul>
          <h3 className="text-xl font-bold text-gray-800 mb-2">Checklist da imagem (mnemónico FOCUS):</h3>
          <ul className="list-disc pl-5 space-y-2">
            <li><strong className="text-purple-600">F</strong>ocus nítido em vasos finos;</li>
            <li><strong className="text-purple-600">O</strong>bstruções ausentes (pálpebra, cílios);</li>
            <li><strong className="text-purple-600">C</strong>entralização (mácula centrada ou disco conforme protocolo);</li>
            <li><strong className="text-purple-600">U</strong>niformidade de iluminação;</li>
            <li><strong className="text-purple-600">S</strong>em artefatos (reflexos, poeira).</li>
          </ul>
          <p className="mt-4">Repetir a imagem se o campo for menor que uma Graduação “7/10” em nitidez ou contraste.</p>
        </Section>

        <Section
          title="Checklist Sistemático de Interpretação"
          imageUrl="https://placehold.co/600x300/F59E0B/FFFFFF?text=Checklist+de+Interpretacao"
          imageAlt="[Diagrama de um checklist de interpretação de retinografia]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>
              <strong className="text-indigo-600">Identificação & Orientação</strong>: Confirmar olho, lateridade, data, midríase.
            </li>
            <li>
              <strong className="text-indigo-600">Disco Óptico</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>Tamanho (pequeno {'<'} 1,5 mm; grande {'>'} 2,2 mm).</li>
                <li>Cor: róseo-alaranjado normal; palidez difusa (neuropatia), setor nasal (compressão quiasmática).</li>
                <li>Escavação: C/D global e setorial; procurar notch, hemorragia de borda, fosseta adquirida.</li>
                <li>Rima neural: aplicar regra ISNT (Inferior {'>'} Superior {'>'} Nasal {'>'} Temporal).</li>
              </ul>
            </li>
            <li>
              <strong className="text-indigo-600">Vasos Retinianos</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>Calibre arteriolar vs venoso, cruzamentos, tortuosidade.</li>
                <li>Lesões: cobreado-prateado, microaneurismas, neovasos (NVD/NVE), sheathing.</li>
              </ul>
            </li>
            <li>
              <strong className="text-indigo-600">Mácula</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>Reflexo foveal, pigmento, drusas, edema (sinal em anel circinado), hemorragias puntiformes, membranas epirretinianas.</li>
              </ul>
            </li>
            <li>
              <strong className="text-indigo-600">Retina Média (Arcadas Vasculares)</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>Algodões-algodão (isquemia RNFL), exsudatos duros, hemorragias em chama ou punctiformes.</li>
              </ul>
            </li>
            <li>
              <strong className="text-indigo-600">Periferia</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>Degenerações lattice, buracos, rasgaduras, nevos, retinosquise.</li>
              </ul>
            </li>
            <li>
              <strong className="text-indigo-600">Camada de Fibras Nervosas da Retina (RNFL)</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>No red-free: estriações brilhantes contínuas; defeito em cunha = perda axonal.</li>
              </ul>
            </li>
            <li>
              <strong className="text-indigo-600">Coróide/EPR</strong>: Atrofia em “geographic”, padrão em lesões polipoidais (ICG).
            </li>
            <li>
              <strong className="text-indigo-600">Documentação Seriada</strong>: Comparar lado a lado; usar softwares de image-tracking.
            </li>
          </ul>
        </Section>

        <Section
          title="Disco Óptico em Detalhes"
          imageUrl="https://placehold.co/600x300/D97706/FFFFFF?text=Disco+Optico"
          imageAlt="[Imagem detalhada do disco óptico do olho]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>
              <strong className="text-indigo-600">Escavação/disco (C/D)</strong>: Normal até 0,6; vertical {'>'} horizontal ou rápido aumento = suspeita.
            </li>
            <li>
              <strong className="text-indigo-600">Hemorragia de borda (em chama/“Drance”)</strong>: Risco de progressão, típico no glaucoma de pressão normal.
            </li>
            <li>
              <strong className="text-indigo-600">Anel neuro-retiniano</strong>: Perda focal = notch.
            </li>
            <li>
              <strong className="text-indigo-600">Atrofia peripapilar</strong>:
              <ul className="list-circle pl-6 mt-2 space-y-2">
                <li>**Alfa** (hipo/hiper-pigmentação do EPR) – pouca correlação.</li>
                <li>**Beta** (ausência de EPR e coriocapilar) – forte associação a glaucoma quando {'\u2265'} 360°.</li>
              </ul>
            </li>
          </ul>
        </Section>

        <Section
          title="Análise Vascular"
          imageUrl="https://placehold.co/600x300/EF4444/FFFFFF?text=Vasos+Retinianos"
          imageAlt="[Imagem de vasos retinianos mostrando alterações vasculares]"
        >
          <div className="overflow-x-auto">
            <table className="min-w-full bg-white border border-gray-200 rounded-lg">
              <thead>
                <tr className="bg-gray-100 border-b">
                  <th className="px-4 py-2 text-left text-sm font-semibold text-gray-700">Achado</th>
                  <th className="px-4 py-2 text-left text-sm font-semibold text-gray-700">Significado Clínico</th>
                </tr>
              </thead>
              <tbody>
                <tr className="border-b">
                  <td className="px-4 py-2">Estreitamento arteriolar difuso</td>
                  <td className="px-4 py-2">Hipertensão crónica</td>
                </tr>
                <tr className="border-b">
                  <td className="px-4 py-2">AV-nicking (cruzamento patológico)</td>
                  <td className="px-4 py-2">Hipertensão moderada-grave</td>
                </tr>
                <tr className="border-b">
                  <td className="px-4 py-2">Fita de cobre/prata</td>
                  <td className="px-4 py-2">Esclerose avançada</td>
                </tr>
                <tr className="border-b">
                  <td className="px-4 py-2">Tortuosidade + microaneurismas</td>
                  <td className="px-4 py-2">Retinopatia diabética inicial</td>
                </tr>
                <tr className="border-b">
                  <td className="px-4 py-2">Neovascularização de disco/margem (NVD)</td>
                  <td className="px-4 py-2">Isquemia severa, risco de hemorragia vítrea</td>
                </tr>
                <tr>
                  <td className="px-4 py-2">Vénulas em “rosário”</td>
                  <td className="px-4 py-2">Doença falciforme ou DR proliferativa</td>
                </tr>
              </tbody>
            </table>
          </div>
        </Section>

        <Section
          title="Mácula"
          imageUrl="https://placehold.co/600x300/A855F7/FFFFFF?text=Macula+Ocular"
          imageAlt="[Imagem da mácula ocular]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>
              <strong className="text-indigo-600">Reflexo foveal ausente</strong> {'\u2192'} edema cistoide ou membrana epirretiniana.
            </li>
            <li>
              <strong className="text-indigo-600">Drusas amarelas</strong> {'\u2192'} DMRI seca; avaliar padrão, número, confluência.
            </li>
            <li>
              <strong className="text-indigo-600">Hemorragia sub-retiniana ou exsudato duro em anel</strong> {'\u2192'} DR com edema macular ou neovasculopatia coroide.
            </li>
            <li>
              <strong className="text-indigo-600">Pigmento {'\u2191'} / Atrofia</strong> {'\u2192'} degeneração macular miópica, corioretinopatias.
            </li>
          </ul>
        </Section>

        <Section
          title="Retina Média e Periferia"
          imageUrl="https://placehold.co/600x300/7C3AED/FFFFFF?text=Retina+Periferica"
          imageAlt="[Imagem da retina média e periferia]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>
              <strong className="text-indigo-600">Microaneurismas, exsudatos duros, hemorragias blot</strong> = DR não-proliferativa.
            </li>
            <li>
              <strong className="text-indigo-600">Algodões-algodão</strong> = oclusão de arteríola precapilar; investigar hipertensão maligna, vasculites, HIV.
            </li>
            <li>
              <strong className="text-indigo-600">Lacuna corioretiniana</strong> (atrofia focal) em alta miopia.
            </li>
            <li>
              <strong className="text-indigo-600">Degeneração lattice</strong>: áreas alongadas, pigmentadas; predisposição a rasgadura e descolamento.
            </li>
          </ul>
        </Section>

        <Section
          title="Documentação e Tele-oftalmologia"
          imageUrl="https://placehold.co/600x300/3B82F6/FFFFFF?text=Teleoftalmologia"
          imageAlt="[Imagem de uma tela de computador com dados de retinografia para teleoftalmologia]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>Armazenar metadados (nome, idade, midríase, OD/OS, hora).</li>
            <li>
              A **Teleretinografia** (protocolo 1-campo macular ou ETDRS 7-campos) detecta {'\u2265'} mild DR com sensibilidade {'>'} 85%.
            </li>
            <li>O relatório deve incluir: qualidade, campo, descrição de cada compartimento, comparação com exames prévios e plano de conduta.</li>
          </ul>
        </Section>

        <Section
          title="Limitações e Exames Complementares"
          imageUrl="https://placehold.co/600x300/1D4ED8/FFFFFF?text=OCT+Ocular"
          imageAlt="[Imagem de um exame OCT ocular]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>
              A imagem bidimensional da retinografia não substitui a oftalmoscopia binocular para o relevo de papila/periferia extrema.
            </li>
            <li>
              Opacidades de mídia (catarata, vítreo turvo) e má fixação podem reduzir a nitidez.
            </li>
            <li>
              **OCT (tomografia de coerência óptica)** quantifica a espessura macular e RNFL; angiografia OCT avalia o fluxo capilar sem contraste.
            </li>
          </ul>
        </Section>

        <Section
          title="Perguntas de Revisão"
          imageUrl="https://placehold.co/600x300/F97316/FFFFFF?text=Perguntas+de+Revisao"
          imageAlt="[Imagem de um ponto de interrogação simbolizando perguntas de revisão]"
        >
          <ul className="list-disc pl-5 space-y-3">
            <li>Quais passos você segue para garantir a qualidade da imagem antes de interpretar uma retinografia?</li>
            <li>Como diferenciar palidez de disco óptico de perda de RNFL ao filtro verde?</li>
            <li>Descreva três sinais retinográficos de hipertensão arterial sistémica.</li>
            <li>Qual o valor-chave de C/D que exige investigação de glaucoma e porquê?</li>
            <li>Explique por que a atrofia β peripapilar é considerada marcador de dano glaucomatoso.</li>
          </ul>
        </Section>

        <Section title="Referências Recomendadas">
          <ul className="list-disc pl-5 space-y-2">
            <li>AAO Basic & Clinical Science Course 2024 – Fundamentals and Principles of Ophthalmology.</li>
            <li>BCSC Retina & Vitreous (Vol. 2).</li>
            <li>Monteiro MLR. Avaliação da camada de fibras nervosas da retina nas afecções neuroftálmicas. Rev Bras Oftalmol 2012. (<a href="https://www.scielo.br" target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline">scielo.br</a>)</li>
            <li>Fundus Photography — Wikipédia (acesso jun 2025). (<a href="https://en.wikipedia.org" target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline">en.wikipedia.org</a>)</li>
          </ul>
        </Section>
      </main>

      {/* Tailwind CSS Script - MUST be included for Tailwind to work */}
      <script src="https://cdn.tailwindcss.com"></script>
      {/* Inter Font - MUST be included for Inter font to work */}
      <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet" />
      <style>
        {`
          body {
            font-family: 'Inter', sans-serif;
          }
          .list-circle {
            list-style-type: circle;
          }
        `}
      </style>
    </div>
  );
};

export default App;
