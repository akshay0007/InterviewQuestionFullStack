package org.example;

import java.util.*;
import java.util.concurrent.Executors;
import java.util.stream.Collectors;

public class JavaStreamUtils {
    public static void main(String[] args) {
        JavaStreamUtils validator = new JavaStreamUtils();
        validator.test();
    }


    public void test() {
        List<Employee> employeeList = createemployee();
        Double value = 0D;
       Map<String,List<Employee>> data= employeeList.stream()
                .collect(Collectors.groupingBy(Employee::getCountry,Collectors.toList()));
        System.out.println(data);
//        Executors.newFixedThreadPool(1);
//        Executors.newCachedThreadPool();
//        Executors.newScheduledThreadPool()
//        System.out.println(value);
//        employeeList.stream().collect(Collectors.toMap(Employee::getCountry,e->e))
//                .entrySet().stream().sorted((e1,e2)->(e1.getValue().getName().compareTo(e2.getValue().getName())))
//                .collect(Collectors.toList());
//        employeeList.stream().sorted((e1,e2)->e1.getName().compareTo(e2.getName()))
//                .collect(Collectors.toList()).forEach(System.out::println);
//        Map<String, List<Employee>> collect = employeeList.stream()
//                .collect(Collectors.groupingBy(Employee::getName,HashMap::new,  Collectors.toList()));
//        collect.entrySet().stream().map(entry->entry.getValue())
//                .flatMap(Collection::stream);

//        employeeList.stream().collect(Collectors.toMap(employee -> employee.getName(), e -> e, (k1, k2) -> k1));
//        System.out.println(employeeList.stream().collect(Collectors.groupingBy((Employee e)->{
//            return e.getCountry();
//        },Collectors.mapping(e->e.getName().toUpperCase(),Collectors.toList()))));
        Map<String, Employee> obj = employeeList.stream().collect(Collectors.toMap(e -> e.getCountry(), e -> e,(e1,e2)->e1));
        System.out.println(obj);
        Executors.newSingleThreadExecutor();
        PriorityQueue a=new PriorityQueue();
        System.out.println(employeeList.stream()
                .collect(Collectors.groupingBy(e->e.getCountry(),
                        Collectors.mapping(e->e.getName(),Collectors.toList()))));
//        System.out.println(employeeList.stream()
//                .collect(Collectors.toMap((Employee e)->e.getCountry(), (Employee e)->e.getName(), (e1,e2)->{
//                    return e1;
//                })));

//        System.out.println(employeeList.stream()
//                .collect(Collectors.groupingBy((Employee e)->e.getCountry(),
//                        Collectors.mapping(e->e.getName().toUpperCase(),Collectors.toList())
//        )));
        System.out.println(employeeList.stream().collect(Collectors.groupingBy((Employee e) -> e.getCountry().equals("US")
                , Collectors.mapping(e -> e.getName().toUpperCase(), Collectors.toList()))));
//        System.out.println(employeeList.stream().collect(Collectors.toMap((e) -> e.getCountry(), e -> e.getSalary(),
//                (salaryOld,salaryNew) -> {
//                    return salaryNew;
//                })));
//        System.out.println(employeeList.stream().collect(Collectors.groupingBy((Employee e)->e.getCountry().equals("US"))));
//        System.out.println(employeeList.stream().collect(Collectors.partitioningBy((Employee e)->e.getCountry().equals("IN"),Collectors.counting())));
//        System.out.println(employeeList.stream().collect(Collectors.maxBy(Comparator.comparing((Employee e)->e.getSalary()))).get());
//        System.out.println(employeeList);
    }


    public List<Employee> createemployee() {
        Employee employee1 = new Employee("name1", "US", 12);
        Employee employee2 = new Employee("name1", "US", 22);
        Employee employee3 = new Employee("name1", "IN", 333);
        Employee employee4 = new Employee("name4", "US", 44);
        Employee employee5 = new Employee("name5", "UK", 4);
        Employee employee6 = new Employee("name6", "UK", 55);
        return Arrays.asList(employee1, employee2, employee3, employee4, employee5, employee6);
    }

    class Employee {
        String name;
        String country;
        int salary;
        }

}



Median Of List--

List<Integer> list = IntStream.rangeClosed(1, 10).boxed().collect(Collectors.toList());

        Integer answ = list.size() % 2 == 0 ?
                list.stream().sorted().skip((list.size() / 2) - 1).limit(2).reduce(0, Integer::sum)/2
                : list.stream().sorted().skip((list.size() - 1) / 2).limit(1).reduce(0, Integer::sum);
        System.out.println(answ);

