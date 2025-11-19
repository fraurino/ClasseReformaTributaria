# 💼 Reforma Tributária — Classe Pascal (Delphi)

> 🚀 **Simplifique. Adapte. Atualize-se.**  
> O Brasil mudou — e o seu sistema precisa acompanhar.  
> Conheça a classe **Funções Adicionais RT**, a solução prática e auxiliar para desenvolvedores Delphi se adequarem à **Reforma Tributária** com alta performance.

---

![License: Proprietary](https://img.shields.io/badge/license-Proprietary-red.svg)
![Status](https://img.shields.io/badge/status-Active-success.svg)
![Delphi](https://img.shields.io/badge/Delphi-Compatible-blue.svg)
![Lazarus](https://img.shields.io/badge/Lazarus-Compatible-orange.svg)



---
## 📢 Status dos Grupos de WhatsApp 
<!-- STATUS DO GRUPO (GitHub-friendly) -->

<div align="left">

  <p style="font-size: 16px;">
    ✅ <strong>Primeira turma</strong> no grupo do WhatsApp 
    <span style="color: #03c96b; font-weight: 600;">REALIZADA</span> com sucesso!
  </p>

  <p style="font-size: 16px;">
    🚀 <strong>2ª turma</strong> já 
    <span style="color: #03c96b; font-weight: 600;">LIBERADA</span> — garanta sua vaga e convite seus amigos e parceiros programadores!
  </p>

  <a href="https://chat.whatsapp.com/J3B50x4M0F72Tc2K8CVN3x" 
     target="_blank"
     style="background-color: #25D366; 
            color: white; 
            padding: 10px 20px; 
            border-radius: 8px; 
            text-decoration: none; 
            font-weight: bold; 
            display: inline-block;
            margin-top: 10px;">
    👉 Entrar na 2ª Turma Agora
  </a>

</div>

---

## 🌐 Acesse o site oficial
👉 [https://rt.aurino.com.br](https://rt.aurino.com.br/?utm_source=github&utm_medium=readme&utm_campaign=reforma_tributaria)

---

## 🧠 O que é a **Classe RT**

A **Classe Reforma Tributária (TFuncoesAdicionaisRT)** foi desenvolvida para simplificar a adequação de sistemas ERP, PDV e emissores fiscais à nova estrutura da **CBS** e **IBS**, com base nas normas oficiais da Reforma Tributária.

✔️ **Compatível com Delphi e Lazarus (99%)**  
✔️ **Códigos e cálculos baseados na legislação vigente**  
✔️ **Automação completa das regras tributárias CBS/IBS**  
✔️ **Integração modular e rápida com sistemas existentes**

---

## ⚙️ Recursos Principais

| Recurso | Descrição |
|----------|------------|
| 🔍 **Cálculo CBS/IBS** | Processamento automático |
| 🧾 **Simulação Tributária** | Geração e validação de tributos em tempo real |
| 🔄 **Adequação Contábil** | Integração direta com sistemas ERP e fiscais |

---

## 💡 Por que usar?

💬 *“Enquanto muitos ainda estão tentando entender as mudanças, você pode estar implementando a solução.”*

A **Funções Adicionais RT** é uma **ferramenta de transição e automação fiscal**, pronta para o novo modelo tributário brasileiro, economizando **semanas de estudo, testes e desenvolvimento**.

✅ Reduz custos e riscos de erros manuais  
✅ Garante conformidade com as novas regras tributárias nos ambientes de homologação 
✅ Acelera o tempo de adequação do seu software  
✅ É uma ferramenta auxiliar para desenvolvimento

---
## 👨‍💻Fluxo da Implementação
<img width="805" height="820" alt="image" src="https://github.com/user-attachments/assets/2bf7908f-7e54-4808-896f-15dde2bfa7c3" />

## 🔧 Exemplo de Implementação com Reforma Tributária

Abaixo segue um exemplo de como integrar a classe **Funções Adicionais RT** ao processo de emissão da NFe utilizando ACBr:

```pascal
procedure EmitirNFeComReformaTributaria;
var
  i: Integer;
begin
  try
    { ===== ETAPA 1: VALIDAÇÃO ===== }
    if not TFuncoesAdicionaisRT.LerINI then
    begin
      ShowMessage('Reforma Tributária não ativa');
      Exit;
    end;

    { ===== ETAPA 2: PREENCHER CABEÇALHO ===== }
    PreencherIdentificacao;
    PreencherEmitente;
    PreencherDestinatario;

    { ===== ETAPA 3: PROCESSAR PRODUTOS COM RT ===== }
    if not queryItem.Active then
      queryItem.Open;

    queryItem.First;
    while not queryItem.Eof do
    begin
      with ACBrNFe1.NotasFiscais.Items[0].NFe.Det.Add do
      begin
        Prod.nItem := queryItem.RecNo;
        Prod.cProd := queryItem.FieldByName('CODIGO').AsString;
        Prod.cEAN  := queryItem.FieldByName('EAN').AsString;
        Prod.xProd := queryItem.FieldByName('DESCRICAO').AsString;
         // ... demais procedimentos ...

        Imposto.vTotTrib := queryItem.FieldByName('VLR_TRIBUTOS').AsFloat;

        with Imposto.ICMS do
        begin
          // ... demais procedimentos ...
        end;

        with Imposto.PIS do
        begin
           // ... demais procedimentos ...
        end;

        with Imposto.COFINS do
        begin
           // ... demais procedimentos ...
        end;

        Nota_Produto_IVA; /// <<<< REFORMA TRIBUTÁRIA 
      end;

      queryItem.Next;
    end;

    { ===== ETAPA 4: CONSOLIDAR TOTAIS ===== }
    Nota_TotalIVA; /// <<<< REFORMA TRIBUTÁRIA

    { ===== ETAPA 5: NFe PADRÃO ===== }
    PreencherTransporte;
    PreencherCobranca;

    { ===== ETAPA 6: ASSINAR E TRANSMITIR ===== }
    ACBrNFe1.Assinar;
    ACBrNFe1.Validar;
    ACBrNFe1.Enviar(lote, imprimir, sincrono, compactar);
    
  except
    on E: Exception do
      ShowMessage('Erro na emissão: ' + E.Message);
  end;
end;
```


---

## 👨‍💻 Para quem é

- Desenvolvedores **Delphi**
- Empresas de software **fiscal e contábil**
- Analistas tributários e **consultores fiscais**
- Projetos que exigem adequação a **CBS/IBS**
- Startups e ERPs que buscam **compliance automatizado**

---

## 📦 Como adquirir

Acesse a compra coletiva exclusiva 👇  
🔗 [https://rt.aurino.com.br](https://rt.aurino.com.br/?utm_source=github&utm_medium=readme&utm_campaign=reforma_tributaria)

Assim que o número mínimo de participantes for atingido,  
**a classe é entregue automaticamente a todos os pagantes**.

---

> ⚠️ **Atenção:** Este repositório é de uso **comercial** e **protegido por direitos autorais.**  
> O acesso e uso do código são restritos.
> 👉[https://rt.aurino.com.br](https://rt.aurino.com.br/?utm_source=github&utm_medium=readme&utm_campaign=reforma_tributaria)

---

📜 **Licença Comercial Restrita**  
Este projeto **não é open source**.  
Seu conteúdo é disponibilizado apenas para **demonstração técnica e marketing comercial**.  
© 2025 — Todos os direitos reservados.

> ⚖️ **Aviso Legal:**  
> Todo o conteúdo contábil, tributário e fiscal apresentado nesta classe tem caráter **técnico e informativo**.  
> As **interpretações e aplicações práticas** devem sempre ser **validadas com o contador responsável** ou o departamento fiscal da empresa.  
> A Classe não substitui a consultoria contábil profissional e não se responsabiliza por decisões tributárias sem orientação especializada.
> A Classe pode cometer erros. Por isso, lembre-se de conferir informações relevantes e juntamente com sua contabilidade.

---

### ⭐ Apoie o projeto
Se este projeto lhe inspirou ou ajudou:
- Dê uma ⭐ aqui no GitHub  
- Compartilhe com outros desenvolvedores Delphi  
- Acompanhe as atualizações no portal oficial  

> 🧠 *Reforma Tributária não é apenas sobre impostos — é sobre preparar o seu sistema para o futuro.*
