<template>
  <main class="main bg-light">
    <section class="policy" v-html="policyInfo"></section>
  </main>
</template>

<script>
  import {mapGetters, mapActions} from 'vuex';

  export default {
    name: "Policy",
//     data() {
//       return {
//         policyHtml: `
//         <div class="container pb-5">
// 		<div class="row">
// 			<div class="col-lg-12">
// 				<span class="eyebrow mb-1 text-primary"></span>
// 				<h2>Политика обработки персональных данных</h2>
// 			</div>
// 		</div>
// 		<div class="row">
// 			<div class="col">
// 				<p class="p1"><span class="s1"><b>ПОЛИТИКА ОБРАБОТКИ ПЕРСОНАЛЬНЫХ ДАННЫХ</b></span></p><ol class="ol1">
// <li class="li2"><b></b><span class="s2"><b>Общие положения</b></span></li>
// <ol class="ol1">
// <li class="li2"><span class="s1">Данная Политика обработки персональных данных (далее – «Политика») определяет порядок обработки персональных данных и меры по обеспечению безопасности персональных данных в ООО «Мерчерри» (ОГРН 1187746921560, далее – «Оператор»).</span></li>
// <li class="li2"><span class="s1">Обработка персональных данных осуществляется в соответствии с положениями Федерального закона №152-ФЗ «О персональных данных» от 27.07.2006 г. и иными нормативно-правовыми актами Российской Федерации, регулирующими обработку персональных данных.</span></li>
// <li class="li2"><span class="s1">Цели обработки персональных данных:</span></li>
// <ol class="ol1">
// <li class="li2"><span class="Apple-tab-span">	</span>1.3.1.<span class="s1">Идентификация Субъекта персональных данных (далее – «Субъект»);</span></li>
// <li class="li2"><span class="Apple-tab-span">	</span>1.3.2.<span class="s1">Взаимодействие с Субъектом, в том числе направление уведомлений, запросов и информации, касающихся услуг Оператора, а также обработка запросов и заявок от Субъекта, а также обеспечение взаимодействия между Субъектом и другими пользователями Платформы Mercherry;</span></li>
// <li class="li2"><span class="Apple-tab-span">	</span>1.3.3.<span class="s1">Оказание услуг Субъекту Оператором;</span></li>
// <li class="li2"><span class="Apple-tab-span">	</span>1.3.4.<span class="s1">Передача персональных данных Субъекта третьим лицам с согласия Субъекта;</span></li>
// <li class="li2"><span class="Apple-tab-span">	</span>1.3.5.<span class="s1">Заключение и исполнение договоров и соглашений между Оператором и Субъектом, Субъектом и другими пользователями Платформы Mercherry .</span></li>
// </ol>
// <li class="li2"><span class="s1">Под обработкой персональных данных Оператором понимается действие (операция) или совокупность действий (операций) с персональными данными, включая сбор, запись, систематизацию, накопление, хранение, уточнение (обновление, изменение), извлечение, использование, передачу (распространение, предоставление, доступ), обезличивание, блокирование, удаление, уничтожение персональных данных.</span></li>
// </ol>
// </ol><ol class="ol1">
// <li class="li2"><b></b><span class="s2"><b>Принципы и условия обработки персональных данных</b></span></li>
// <ol class="ol1">
// <li class="li2"><span class="s1">Обработка персональных данных Оператором осуществляется на основе следующих принципов:<span class="Apple-converted-space">&nbsp;</span></span></li>
// </ol>
// </ol><ul class="ul1">
// <li class="li2"><span class="s3"></span><span class="s1">законности и обязательного получения согласия Субъекта персональных данных в предусмотренных законом случаях;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">ограничения обработки персональных данных достижением конкретных, заранее определенных и законных целей;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">недопущения обработки персональных данных, несовместимой с целями сбора персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">недопущения объединения баз данных, содержащих персональные данные, обработка которых осуществляется в целях, несовместимых между собой;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">обработки только тех персональных данных, которые отвечают целям их обработки;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">соответствия содержания и объема обрабатываемых персональных данных заявленным целям обработки;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">недопущения обработки персональных данных, избыточных по отношению к заявленным целям их обработки;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">обеспечения точности, достаточности и актуальности персональных данных по отношению к целям обработки персональных данных;<span class="Apple-converted-space">&nbsp;</span></span></li>
// <li class="li2"><span class="s3"></span><span class="s1">уничтожения либо обезличивания персональных данных по достижении целей их обработки или в случае утраты необходимости в достижении этих целей, если иное не предусмотрено федеральным законом.</span></li>
// </ul><ol class="ol1">
// <ol class="ol1">
// <li class="li2"><span class="s1">Оператор производит обработку персональных данных с Согласия Субъекта на обработку его персональных данных.</span></li>
// <li class="li2"><span class="s1">Оператор и иные лица, получившие доступ к персональным данным, обязаны не раскрывать третьим лицам и не распространять персональные данные без Согласия Субъекта персональных данных, если иное не предусмотрено законодательством Российской Федерации.</span></li>
// <li class="li2"><span class="s1">Оператор вправе поручить обработку персональных данных другому лицу с Согласия Субъекта персональных данных, если иное не предусмотрено федеральным законом, на основании заключаемого с этим лицом договора. Лицо, осуществляющее обработку персональных данных по поручению Оператора, обязано соблюдать принципы и правила обработки персональных данных, предусмотренные законодательством Российской Федерации и настоящей Политикой.</span></li>
// <li class="li2"><span class="s1">Трансграничная передача персональных данных на территории иностранных государств не будет осуществляться Оператором.</span></li>
// </ol>
// </ol><ol class="ol1">
// <li class="li3"><b></b><span class="s2"><b>Права субъекта персональных данных</b></span></li>
// <ol class="ol1">
// <li class="li2"><span class="s1">Субъект персональных данных имеет право на получение у Оператора информации, касающейся обработки его персональных данных, если такое право не ограничено в соответствии с федеральными законами. Субъект персональных данных вправе требовать от Оператора уточнения его персональных данных, их блокирования или уничтожения в случае, если персональные данные являются неполными, устаревшими, неточными, незаконно полученными или не являются необходимыми для заявленной цели обработки, а также принимать предусмотренные законом меры по защите своих прав.</span></li>
// <li class="li2"><span class="s1">Если Субъект персональных данных считает, что Оператор осуществляет обработку его персональных данных с нарушением требований законодательство Российской Федерации или иным образом нарушает его права и свободы, субъект персональных данных вправе обжаловать действия или бездействие Оператора в уполномоченный орган по защите прав субъектов персональных данных или в судебном порядке.</span></li>
// </ol>
// <li class="li3"><b></b><span class="s2"><b>Обеспечение безопасности персональных данных</b></span></li>
// <ol class="ol1">
// <li class="li2"><span class="s1">Безопасность персональных данных, обрабатываемых Оператором, обеспечивается реализацией правовых, организационных и технических мер, необходимых для обеспечения требований законодательства Российской Федерации в области защиты персональных данных.</span></li>
// <li class="li2"><span class="s1">Для предотвращения несанкционированного доступа к персональным данным Оператором применяются следующие организационно-технические меры:</span></li>
// </ol>
// </ol><ul class="ul1">
// <li class="li2"><span class="s3"></span><span class="s1">назначение должностных лиц, ответственных за организацию обработки и защиты персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">ограничение состава лиц, допущенных к обработке персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">ознакомление субъектов с требованиями федерального законодательства и нормативных документов Оператора по обработке и защите персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">организация учета, хранения и обращения носителей, содержащих информацию с персональными данными;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">определение угроз безопасности персональных данных при их обработке, формирование на их основе моделей угроз;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">разработка на основе модели угроз системы защиты персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">проверка готовности и эффективности использования средств защиты информации;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">разграничение доступа пользователей к информационным ресурсам и программно-аппаратным средствам обработки информации;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">регистрация и учет действий пользователей информационных систем персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">использование антивирусных средств и средств восстановления системы защиты персональных данных;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">применение в необходимых случаях средств межсетевого экранирования, обнаружения вторжений, анализа защищенности и средств криптографической защиты информации;</span></li>
// <li class="li2"><span class="s3"></span><span class="s1">организация пропускного режима на территорию Оператора, охраны помещений с техническими средствами обработки персональных данных.<span class="Apple-converted-space">&nbsp;</span></span></li>
// </ul><p class="p1">
//
//
//
//
// <style type="text/css">
// p.p1 {margin: 0.0px 0.0px 6.0px 0.0px; text-align: center; font: 14.0px 'Trebuchet MS'; color: #000000; -webkit-text-stroke: #000000}
// li.li2 {margin: 0.0px 0.0px 6.0px 0.0px; text-align: justify; font: 14.0px 'Trebuchet MS'; color: #000000; -webkit-text-stroke: #000000}
// li.li3 {margin: 0.0px 0.0px 6.0px 0.0px; font: 14.0px 'Trebuchet MS'; color: #000000; -webkit-text-stroke: #000000}
// span.s1 {font-kerning: none}
// span.s2 {text-decoration: underline ; font-kerning: none}
// span.s3 {font: 14.0px Symbol}
// span.Apple-tab-span {white-space:pre}
// ol.ol1 {list-style-type: decimal}
// ul.ul1 {list-style-type: disc}
// </style>
//
//
//
//
//
//
//
//
//
// </p><ol class="ol1">
// <li class="li2"><b></b><span class="s2"><b>Заключительные положения</b></span></li>
// <ol class="ol1">
// <li class="li2"><span class="s1">Иные права и обязанности Оператора в связи с обработкой персональных данных определяются законодательством Российской Федерации в области персональных данных.</span></li>
// <li class="li2"><span class="s1">Оператор имеет право вносить изменения в настоящую Политику. При внесении изменений в актуальной редакции указывается дата последнего обновления. Новая редакция Политики вступает в силу с момента ее размещения на веб-сайте http://mercherry.ru/, если иное не предусмотрено новой редакцией Политики.<span class="Apple-converted-space">&nbsp;</span></span></li>
// <li class="li2"><span class="s1">Субъект персональных данных, который дает Согласие на обработку персональных данных, присоединяется к данной Политике с момента дачи такого Согласия. Условия Согласия на обработку персональных данных имеют преимущественную силу перед условиями Политики.</span></li>
// <li class="li2"><span class="s1">Работники Оператора, виновные в нарушении норм, регулирующих обработку и защиту персональных данных, несут материальную, дисциплинарную, административную, гражданско-правовую или уголовную ответственность в порядке, установленном законодательством Российской Федерации.</span></li>
// </ol>
// </ol><ol class="ol1"><ol class="ol1">
// </ol>
// </ol><style type="text/css">
// p.p1 {margin: 0.0px 0.0px 6.0px 0.0px; text-align: center; font: 14.0px 'Trebuchet MS'; color: #000000; -webkit-text-stroke: #000000}
// li.li2 {margin: 0.0px 0.0px 6.0px 0.0px; text-align: justify; font: 14.0px 'Trebuchet MS'; color: #000000; -webkit-text-stroke: #000000}
// li.li3 {margin: 0.0px 0.0px 6.0px 0.0px; font: 14.0px 'Trebuchet MS'; color: #000000; -webkit-text-stroke: #000000}
// span.s1 {font-kerning: none}
// span.s2 {text-decoration: underline ; font-kerning: none}
// span.s3 {font: 14.0px Symbol}
// span.Apple-tab-span {white-space:pre}
// ol.ol1 {list-style-type: decimal}
// ul.ul1 {list-style-type: disc}
// </style>			</div>
// 		</div>
// 	</div>`
//       }
//     },
    computed: {
      ...mapGetters({
        policyInfo: 'policy/policyInfo'
      }),
    },
    methods: {
      ...mapActions({
        policy: 'policy/POLICY'
      })
    },
    created() {
      this.policy();
    }
  }
</script>

<style scoped>

</style>