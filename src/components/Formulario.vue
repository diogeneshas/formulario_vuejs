<template>
  <div class="container">
    <div class="row">
      <div class="col-6 bg-light">
        <span class="fs-4">ENTRADA DE DADOS</span>
        <hr>
        <form>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Nome:</label>
            <div class="col">
              <input type="text" class="form-control" v-model="form.nome">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">E-mail:</label>
            <div class="col">
              <input type="email" class="form-control" v-model="form.email">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Senha:</label>
            <div class="col">
              <input type="password" class="form-control" v-model="form.senha">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Idade:</label>
            <div class="col">
              <input type="number" class="form-control" v-model="form.idade">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Gênero:</label>
            <div class="col">
              <div class="form-check form-check-inline">
                <input class="form-check-input" value="Feminino" type="radio" v-model="form.genero">
                <label class="form-check-label">
                  Feminino
                </label>
              </div>
              <div class="form-check form-check-inline">
                <input class="form-check-input" value="Masculino" type="radio" v-model="form.genero">
                <label class="form-check-label">
                  Masculino
                </label>
              </div>
            </div>
          </div>

          <div class="mb-3 row">
            <label class="col-3 col-form-label">Licença:</label>
            <div class="col">
              <div class="form-check form-switch">
                <input class="form-check-input" type="checkbox" v-model="form.licenca" true-value="SIM"
                  false-value="NÃO">
                <label class="form-check-label">Li e aceito os termos</label>
              </div>
            </div>
          </div>

          <div class="mb-3 row">
            <label class="col-3 col-form-label">Interesses:</label>
            <div class="col">
              <div class="form-check">
                <input class="form-check-input" value="JavaScript" type="checkbox" v-model="form.interesses">
                <label class="form-check-label">
                  JavaScript
                </label>
              </div>
              <div class="form-check">
                <input class="form-check-input" value="VueJS" type="checkbox" v-model="form.interesses">
                <label class="form-check-label">
                  VueJS
                </label>
              </div>
              <div class="form-check">
                <input class="form-check-input" value="Angular" type="checkbox" v-model="form.interesses">
                <label class="form-check-label">
                  Angular
                </label>
              </div>
              <div class="form-check">
                <input class="form-check-input" value="NodeJS" type="checkbox" v-model="form.interesses">
                <label class="form-check-label">
                  NodeJS
                </label>
              </div>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Telefone:</label>
            <div class="col">
              <input type="text" class="form-control" v-maska="'(##) #####-####'" v-model="form.telefone">
              <small class="text-muted">Formato: 11 97777-5555</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Data:</label>
            <div class="col">
              <input type="date" class="form-control" v-model="form.data">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Data/hora local:</label>
            <div class="col">
              <input type="datetime-local" class="form-control" v-model="form.dataHoraLocal">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Mês:</label>
            <div class="col">
              <input type="month" class="form-control" v-model="form.mes">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Semana:</label>
            <div class="col">
              <input type="week" class="form-control" v-model="form.semana">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Hora:</label>
            <div class="col">
              <input type="time" class="form-control" v-model="form.hora">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Cor:</label>
            <div class="col">
              <input type="color" class="form-color" v-model="form.cor">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Valor limite:</label>
            <div class="col">
              <input type="range" class="form-range" min="0" max="100" step="1" v-model="form.alcance">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Escondido:</label>
            <div class="col">
              <input type="hidden" class="form-control">
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Upload:</label>
            <div class="col">
              <input type="file" class="form-control" multiple @change="selecionarArquivos($event)">
            </div>
          </div>
          <div class="mb-3 row">
            <label for="" class="col-3 col-form-label">Cursos:</label>
            <div class="col">
              <select class="form-select" v-model="form.curso">
                <option value="" disabled>-- Selecione uma opcao --</option>
                <option v-for="curso in cursos" :key="curso.id" :value="curso.id">{{ curso.curso }}</option>
              </select>
            </div>
          </div>
          <hr>
          <div class="mb-3 row">
            <div class="col d-flex justify-content-between">
              <button class="btn btn-secondary" type="reset">Limpar</button>
              <button class="btn btn-success" type="button">Enviar (btn)</button>
              <button class="btn btn-success" type="submit">Enviar (submit)</button>
            </div>
          </div>


        </form>
      </div>


      <div class="col-6 text-white bg-secondary" :style="'background-color:' + this.form.cor + '!important'">
        <span class="fs-4">ESTADO DO OBJETO</span>
        <hr>
        <div class="mb-5 row">
          <spam>Estado do objeto</spam>
        </div>

        <span class="fs-4">SAÍDA DE DADOS</span>
        <hr>
        <div class="mb-3 row">
          <spam>Nome: {{ this.form.nome }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>E-mail: {{ this.form.email }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Senha:{{ this.form.senha }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Idade:{{ this.form.idade }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Gênero: {{ form.genero }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Licença:{{ this.form.licenca }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Interesses:</spam>
          <ul>
            <li v-for="(interesse, index) in form.interesses" :key="index">{{ interesse }}</li>
          </ul>
        </div>
        <div class="mb-3 row">
          <spam>Telefone: {{ form.telefone }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Data: {{ $moment(form.data).format('DD/MM/YYYY') }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Data/hora local: {{ form.dataHoraLocal }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Mês: {{ form.mes }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Semana: {{ form.semana }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Hora: {{ form.hora }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Cor: {{ form.cor }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Valor limite: {{ form.alcance }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Escondido: {{ form.escondido }}</spam>
        </div>
        <div class="mb-3 row">
          <spam>Upload:</spam>
          <ul>
            <li v-for="(arquivo, index) in form.arquivos" :key="index">{{ arquivo.name }}</li>
          </ul>
        </div>
        <div class="mb-3 row">
          <spam>Curso: {{ form.curso }}</spam>
        </div>
      </div>
    </div>

  </div>

</template>

<script>


export default {
  name: 'Formulario',
  data() {
    return {
      cursos: [
        { id: 1, curso: 'Banco de Dados Relacionais' },
        { id: 2, curso: 'Desenvolvimento Web Avancado com Vue' },
        { id: 3, curso: 'Curso completo do desenvolvedor NodeJS e MongoDB' }
      ],
      form: {
        nome: '',
        email: '',
        senha: '',
        licenca: 'SIM',
        interesses: [],
        telefone: '',
        data: '',
        dataHoraLocal: '',
        mes: '',
        semana: '',
        cor: '',
        alcance: 5,
        escondido: 'Esse input esta escondido',
        arquivos: {},
        curso: ''
      }
    }
  },
  created() {
  },
  methods: {
    selecionarArquivos(event) {
      console.log(event.target.files)
      this.form.arquivos = event.target.files
    }
  }
}
</script>
