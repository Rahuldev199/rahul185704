
Map<String, Event> map= new HashMap<>();

List<Event> events = Arrays.asList(event, event1, event2, event3, event4);
        events.stream().forEach( e -> {
            if(map.get(e.getDate()+e.getType()) != null){
                Event ev= map.get(e.getDate()+e.getType());
                ev.setKbData(String.valueOf(Double.parseDouble(ev.getKbData())+Double.parseDouble(e.getKbData())));
                ev.setMbData(String.valueOf(Double.parseDouble(ev.getMbData())+Double.parseDouble(e.getMbData())));
                ev.setGbData(String.valueOf(Double.parseDouble(ev.getGbData())+Double.parseDouble(e.getGbData())));
            }else{
                map.put(e.getDate()+e.getType(), e);
            }
        });
