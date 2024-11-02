import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Previsão do Tempo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: PrevisaoPage(),
    );
  }
}

class PrevisaoPage extends StatefulWidget {
  @override
  _PrevisaoPageState createState() => _PrevisaoPageState();
}

class _PrevisaoPageState extends State<PrevisaoPage> {
  List<Previsao> previsoes = [
    Previsao(
      data: '2024-10-23 08:00:00',
      temperatura: 25.0,
      umidade: 50.0,
      luminosidade: 100.0,
      vento: 0.0,
      chuva: 0.0,
      unidade: 'C',
    ),
    Previsao(
      data: '2024-10-23 09:00:00',
      temperatura: 25.0,
      umidade: 50.0,
      luminosidade: 100.0,
      vento: 0.0,
      chuva: 0.0,
      unidade: 'C',
    ),
    Previsao(
      data: '2024-10-23 10:00:00',
      temperatura: 25.0,
      umidade: 50.0,
      luminosidade: 100.0,
      vento: 0.0,
      chuva: 0.0,
      unidade: 'C',
    ),
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Previsão do Tempo'),
      ),
      body: ListView.builder(
        itemCount: previsoes.length,
        itemBuilder: (context, index) {
          return Card(
            margin: EdgeInsets.all(10),
            child: ListTile(
              title: Text('Data: ${previsoes[index].data}'),
              subtitle: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Text(
                      'Temperatura: ${previsoes[index].temperatura}°${previsoes[index].unidade}'),
                  Text('Umidade: ${previsoes[index].umidade}%'),
                  Text('Luminosidade: ${previsoes[index].luminosidade} lux'),
                  Text('Vento: ${previsoes[index].vento} m/s'),
                  Text('Chuva: ${previsoes[index].chuva} mm'),
                ],
              ),
            ),
          );
        },
      ),
    );
  }
}

class Previsao {
  final String data;
  final double temperatura;
  final double umidade;
  final double luminosidade;
  final double vento;
  final double chuva;
  final String unidade;

  Previsao({
    required this.data,
    required this.temperatura,
    required this.umidade,
    required this.luminosidade,
    required this.vento,
    required this.chuva,
    required this.unidade,
  });
}
